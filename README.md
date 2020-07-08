# origin-news
A Chrome plug-in that locates the earliest iterations of news stories.

## Tech Overview

Origin News is a Chrome plug-in that allows users to highlight a section text in a news story and use the plug-in to perform a series of Google (or other search engine) searches that locates the earliest iteration of the selected text. Along with locating the earliest instance of the text, we hope to provide additional metadata about the original site, including the site's ownership and funding sources.

## Lexicon

* **Chrome Plug-in** - A small program that customizes the browser experience, usually some sort of tool.
* **Google API** - Google's programmatic interface for its search engine.

## How It Works

1. The user questions a piece of text (preferably in a news story) and desires to know the original source.
2. The user highlights the questionable text, right-clicks on the highlighted text and selects an **Originate** button in the right-click menu.
3. The plug-in prints the text into a Google search query.
4. The plug-in then initiates an HTTP request(s) to the Google Search API with the quoted text as a the payload.
5. The plug-in receives the results as a series of JSON objects from the Google Search API.
6. The plug-in then scans the results for the results for the earliest date.
7. The plug-in then records prints the domain name into a second API request and sends a GET request to an as yet determined database to gather information about the website's owners/funders.
7. The plug-in then combines the results of the funding database, origin URL, post date, and other metadata, and returns the information to the user.

## Milestones

### Initial Research is Complete
We have the majority of knowledge to complete the initial design of the plugin. This knowledge should include:

* The language the plug-in will be written in
* The overall approach of how the plug-in will work programmatically
* The APIs we'll be using to source our information and their respective behaviors
* The tools required to build the plug-in and maintain our workflow
* The workflows we will use, i.e. how we intend to contribute code and review it

### Initial Design is Complete
We have a decent sketch of how each function will work inside the plug-in and the coding involved to complete that function.

### Successful Programmatic Queries
We have succeeded in writing a set of functions that can access the APIs and return data.

### Successful Script
The script can now be successfully run by simply entering a piece of text into an input field on the command line or other programmatic tool.

### UX Design
The program has been successfully linked to Google Chrome's UI functions and can now accept highlighted text on web pages to begin queries.

## Standing Questions


## Research
