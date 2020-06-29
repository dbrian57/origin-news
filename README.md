# origin-news
A Chrome plug-in that locates the earliest iterations of news stories.

## Tech Overview

Origin News is a Chrome plug-in that allows users to highlight a section text in a news story and use the plug-in to perform a series of Google (or other search engine) searches that locates the earliest iteration of the selected text. Along with locating the earliest instance of the text, we hope to provide additional metadata about the original site, including the site's ownership and funding sources.

## Lexicon

* **Chrome Plug-in** -
* **Google API** -

## How It Works

1. The user questions a piece of text (preferably in a news story) and desires to know the original source.
2. The user highlights the questionable text, right-clicks on the highlighted text and selects an **Originate** button in the right-click menu.
3. The plug-in prints the text into a Google search query.
4. The plug-in then initiates an HTTP request(s) to the Google Search API with the quoted text as a the payload.
5. The plug-in receives the results as a series of JSON objects from the Google Search API.
6. The plug-in then scans the results for the 
