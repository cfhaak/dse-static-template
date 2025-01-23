# Here are some issues you could solve.

## Problem 1

There is a document overview. You can view it in the browser by clicking on "Editionseinheiten". But if you click on a document, nothing happens. Whoever made that page assumed, the tiny link symbol at the beginning of each row would be enough. It isn’t.



### Please change the page, so that clicking on the title or the whole row opens the corresponding document.


If you feel lost, try to do the following:
1. Find the file that is responsible for creating the html file containing the table. Looking at the buidl.xml file organizing the xslts might be a good start.
2. Try to find the xslt that creates the existing link.
3. Move the part responsible for the link to the new location.

### There was a js-library involved in rendering this table. Its called tabulator. Please find the place, where I commented the code responsible for loading it and uncomment it. (It’s in the same file, you just worked with…) See if your links still work. If not, try to fix them.

<br/>

**If you want to try something on your own:** *could you add some more functionality to the table? What could be added? You will have to interact with tabulutor.js to tackle this. Also keep in mind, that the data are heterogenous, so you might have to harmonize them or to exclude some.*


## Problem 2

There are some images contained in the edition xml files, that don’t get rendered in the frontend. Lets take ```data/editions/KrausExample.xml``` as an example. Try to get the images of the document displayed in the frontend.
1. Try to find out, where the images are linked in the xml file.
2. Try to find out, how/where the text image relation is determined in the xml file.
3. Try to find the xslt responsible for rendering the page with the transcribed text.
4. Try to add a little xslt-template to change the behavior, so that the image gets displayed.
5. Add so css to make it look a little better.

*Can you identify a problem in the TEI-XML relating to fact how we handle pages and images of pages?*

## Problem 3
Some of the edited documents contain footnotes. However if you look at the website you just built theres a bunch of problems. One of the strangest behaviors is, that some of the footnotes are linked to main text. But others aren’t.
Try to:
1. Find the XSLT responsible for creating the footnotes in the html files.
2. Try to understand, which elements in the XML files are affected by it and in what way.
3. Try to find a better solution.