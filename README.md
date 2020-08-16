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

### Initial Research is Complete
We have the majority of knowledge to complete the initial design of the plugin. This knowledge should include:

* The language the extension will be written in
* The overall approach of how the extension will work programmatically
* The APIs we'll be using to source our information and their respective behaviors
* The tools required to build the extension and maintain our workflow
* The workflows we will use, i.e. how we intend to contribute code and review it

### Initial Design is Complete
We have a decent sketch of how each function will work inside the extension and the coding involved to complete that function.

### Successful Programmatic Queries
We have succeeded in writing a set of functions that can access the APIs and return data.

### Successful Script
The script can now be successfully run by simply entering a piece of text into an input field on the command line or other programmatic tool.

### UX Design
The program has been successfully linked to Google Chrome's UI functions and can now accept highlighted text on web pages to begin queries.

## Standing Questions
* Should the funding aspect still be a part of this? If we don't find a database with this knowledge, this information may be difficult to come by, especially considering that many of these news sites are likely funded by foreign states.
* ~~Is this a plug-in or an extension? Is there a difference between the two as far as Chrome is concerned? We should get the vernacular correct.~~ **It's definitely an extension. I've updated text throughout.**

## Research
* [Google's API documentation](https://developers.google.com/custom-search/v1/using_rest)
* [Wayback Machine's API docs](https://archive.org/help/wayback_api.php)
* [How to Write a Chrome Extension (plug-in)](https://developer.chrome.com/extensions/getstarted)
* [Example of How to Add an Extension to the Right-Click Menu](https://stackoverflow.com/questions/5193350/chrome-extension-append-functions-to-right-click-menu) - I also think this example does something very similar to what we're doing as far as loading a search query with highlighted text.

## Branch Workflow

When you want to contribute code to this repo, or you want to test stuff in your own environment without messing with the contributions that are already in Master, branch the repo.

To do this, open your command line and navigate to the `origin-news` repo.

Example: `cd desktop/repos/origin-news`

Once inside the repo, you can branch the repo by running the following command:

`git checkout -b <your-last-name>/<name-of-your-branch>`

Example: `git checkout -b brian/bing-test`

This will "make a copy" of the repo that you can work in without fear of messing up any of the original work.

## Make a Pull Request (add your code to the Master branch)

When you are ready to contribute your changes, you need to open a pull request.

To open a pull request, you need to stage all of the changes you made to your working branch.

`git add -A` (if you have any new files)

`git add -u` (if you only made changes to existing files that have already been committed)

Once the files are staged, commit them to your branch:

`git commit -m "<your commit message>"`

Then push the branch to the repo (this will not merge the changes into Master):

`git push`

Once the files have been pushed, open the repo on Github.com. The banner will appear at the top of the repo asking if you want to open a pull request, click it.
