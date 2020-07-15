# origin-news
A Chrome extension that locates the earliest iterations of news stories.

## Tech Overview

Origin News is a Chrome extension that allows users to highlight a section text in a news story and use the extension to perform a series of Google (or other search engine) searches that locates the earliest iteration of the selected text. Along with locating the earliest instance of the text, we hope to provide additional metadata about the original site, including the site's ownership and funding sources.

## Lexicon

* **Chrome extension** - A small program that customizes the browser experience, usually some sort of tool.
* **Google API** - Google's programmatic interface for its search engine.

## How It Works

1. The user questions a piece of text (preferably in a news story) and desires to know the original source.
2. The user highlights the questionable text, right-clicks on the highlighted text and selects an **Originate** button in the right-click menu.
3. The extension prints the text into a Google search query.
4. The extension then initiates an HTTP request(s) to the Google Search API with the quoted text as a the payload.
5. The extension receives the results as a series of JSON objects from the Google Search API.
6. The extension then scans the results for the results for the earliest date.
7. The extension then records prints the domain name into a second API request and sends a GET request to an as yet determined database to gather information about the website's owners/funders.
7. The extension then combines the results of the funding database, origin URL, post date, and other metadata, and returns the information to the user.

## Milestones

### Initial Research is Complete (date completed: )
We have the majority of knowledge to complete the initial design of the plugin. This knowledge should include:

* The language the extension will be written in
* The overall approach of how the extension will work programmatically
* The APIs we'll be using to source our information and their respective behaviors
* The tools required to build the extension and maintain our workflow
* The workflows we will use, i.e. how we intend to contribute code and review it

### Initial Design is Complete (date completed: )
We have a decent sketch of how each function will work inside the extension and the coding involved to complete that function.

### Successful Programmatic Queries (date completed: )
We have succeeded in writing a set of functions that can access the APIs and return data.

### Successful Script (date completed: )
The script can now be successfully run by simply entering a piece of text into an input field on the command line or other programmatic tool.

### UX Design (date completed: )
The program has been successfully linked to Google Chrome's UI functions and can now accept highlighted text on web pages to begin queries.

## Standing Questions
* Should the funding aspect still be a part of this? If we don't find a database with this knowledge, this information may be difficult to come by, especially considering that many of these news sites are likely funded by foreign states.
* ~~Is this a plug-in or an extension? Is there a difference between the two as far as Chrome is concerned? We should get the vernacular correct.~~ **It's definitely an extension.**

## Research
* [Google's API documentation](https://developers.google.com/custom-search/v1/using_rest)
* [Wayback Machine's API docs](https://archive.org/help/wayback_api.php)
* [How to Write a Chrome Extension (plug-in)](https://developer.chrome.com/extensions/getstarted)
* [Example of How to Add an Extension to the Right-Click Menu](https://stackoverflow.com/questions/5193350/chrome-extension-append-functions-to-right-click-menu) - I also think this example does something very similar to what we're doing as far as loading a search query with highlighted text.
