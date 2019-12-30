# data-journalism

>"Data journalism begins in one of two ways: either you have a question that needs data, or a dataset that needs questioning. >Whichever it is, the compilation of data is what defines it as an act of data journalism." ~ Paul Bradshaw

## (1) COURSES

* [Google News Initiative courses](https://newsinitiative.withgoogle.com/training/)
* [Data Journalism courses](https://datajournalism.com/)

## (2) RESEARCH TOOLS

### Advanced Search
* [Structured data testing tool](https://search.google.com/structured-data/testing-tool/u/0/)
* [Google Advanced Search](http://www.googleguide.com/print/adv_op_ref.pdf)
* [Google Alerts](https://www.google.com/alerts)
* [Dataset Search](https://toolbox.google.com/datasetsearch)
* [Public Data Explorer](https://www.google.com/publicdata/directory)

### Verification

When a violent protest, mass-scale accident, or natural hazard unfolds, information tends to get jumbled, causing fear and confusion. With the growing use of technology, we have witnessed innumerable false and fake stories being shared on social networks, including photoshopped images, or re-uploaded diced videos from unrelated events in the past. With increasing frequency, journalists are required to master the skills and expertise to handle the information that circulates on the Internet and elsewhere. Below are some tools that will provide carry out verification of data in the digital age.

* [Fact Check Explorer](https://toolbox.google.com/factcheck/explorer)
* [Wayback machine - Internet archive](https://archive.org/)
* [Google images](https://images.google.com/)
* [InVid](https://www.invid-project.eu/)
* [Watch frame by frame](http://www.watchframebyframe.com/)
* [Youtube DataViewer](https://citizenevidence.amnestyusa.org/)
* [Suncalc.org](https://www.suncalc.org/#/40.1789,-3.5156,3/2019.12.30/23:31/1/3)

### Scraping data

* _Python_: If you know what a terminal or command prompt is and if you are familiar with Excel, Python should be easy for you to pick up. To set up, first install the [Anaconda distribution](https://anaconda.org/) to install Python 3, libraries Requests, Pandas, and BeautifulSoup, and Jupyter Notebooks all at once on your computer.
* If you want to make sure you have a solid foundation to build up on, you might want to learn about the Python syntax first. Check the online beginner tutorials at [LearnPython.org](https://www.learnpython.org/) and the digital book [Python for you and me](https://pymbook.readthedocs.io/en/py3/).
* You can use both the Requests and the BeautifulSoup libraries to write some basic web-scrapers to collect data from the internet.

## (3) DATA ANALYSIS

### Cleaning Data

* One of the most important and oft-neglected steps in any data journalism project is cleaning up raw data. Almost always, when you first get the data you want (or the data you've settled for), it's not yet usable. It's riddled with inconsistencies and doesn't express the relationships you want to analyse. You don't fully understand its parameters yet. Before you can make it interesting, you need to field strip it and put it back together.
* This process is dangerous; there are lots of ways to go wrong and make mistakes without even realising it. When you screw up your data in the process of cleaning it, the best case scenario is that you waste a lot of time, but the worst case scenario is that your ultimate analysis will be wrong because you've unknowingly changed the data.
* If you have a big Excel file or a MySQL table that needs cleaning, don’t just go in there and start drilling holes in the wall. Make a copy and work on that instead. It will make it easier to start over if you screwed up, and, more importantly, you can compare what you’ve got at different stages of cleaning and mutation to make sure it matches up not just with the previous step in your cleaning, but with the starting data.
* Look out for empty values, and especially for pseudo-empty values. Excel files from government agencies are unendingly creative when it comes to weird placeholder characters, and you’ll get data that uses - or * or ~ to fill a blank space. For bonus points, check for extreme value lengths too. If most of the street addresses in your data are about 75 characters long and one of them is 450 characters long, strange things are afoot at the Circle K.
* For every categorical column, check the list of values that exist in the data. Make sure everything that should be there is, and anything that shouldn’t be isn’t. GROUP BY (or its twin SELECT DISTINCT) should become your new best friend. For every numerical column, at least sanity check mins and maxes. Check the ranges of every special data type (e.g. ZIP codes). Don’t assume that all dates will be formatted the same, or even be dates.
* When you’re Grouping things, use COUNT() to see how many items there are in each category. See if all the numbers pass your basic smell test. If they don’t, you probably screwed something up, but if you’re lucky it means there’s a story there. Either way, you want to know.
* Text data sucks. Be careful about whitespace, capitalisation, and character collation in text columns. There could be random whitespace in your cells that breaks your ability to compare or group them. You know that "Paris" and "Paris " are the same, but your database doesn’t. Use TRIM() where it’s reasonable to do so. And remember Veltman’s Law of Character Sets: there will be exactly one é somewhere in your data and you won’t find it until it ruins everything.
* Data can be cleaned via one of the following tools:
* *[Open Refine](http://openrefine.org/)*: Download the free open source software Open Refine onto your computer. Launching the program will open a new page in your browser: ‘localhost:3333’ or ‘127.0.0.1:333’ - openRefine creates a server on your own computer and the browser is connecting to this.
* _Python_: Download the [Jupyter notebooks](https://github.com/winnydejong/pythonforjournalists/tree/master/2%20clean%20data) from Github. Import a CSV-file into your Jupyter Notebook, for some data cleaning. To clean the data you will have to learn how to search and replace values inside a column; how to change the datatype of a column; and how to extract data from a column to populate a new column.
* _R_: is getting more and more popular among Data Journalists worldwide, helping them with on a near-daily basis is the act of cleaning, joining and superficially analysing data.
* _[Amazon Mechanical Turk (MTurk)](https://www.mturk.com/)_: is a crowdsourcing marketplace that makes it easier for individuals and businesses to outsource their processes and jobs to a global distributed workforce who can perform these tasks virtually. This can save time on what can otherwise be a very onerous task.

### Organising Data

* Decide whether to structure your data in a spreadsheet or database: [Spreadsheets vs. Databases](https://github.com/veltman/learninglunches/tree/master/databases)
* Relational databases like MySQL, PostgreSQL and SQLite3 represent and store data in tables and rows. They're based on a branch of algebraic set theory known as relational algebra. Meanwhile, non-relational databases like MongoDB represent data in collections of JSON documents
* Whether you’re using Excel, a relational database, or something else, make sure that your columns/fields are the type you want, and ALL of the data going in matches those types. If you don’t, your data is going to get squeezed through a special decorative mold when you import it and all your candy cane integers will become snowflake text and you won’t even know it’s happening. This is especially important if your data is going to pulled out the other side later to power some sort of cool app, where it’s going to go through the variable type wringer again.

### Statistical Analysis

* Mathematical errors in data analysis can be enough to destroy the credibility of a journalist. Here are some math and statistical tutorials to teach you the basics:
* The 15-page [Excel Tutorial](http://datajournalismcourse.net/download/TutorialExcelWindows.php) which explains further the material that will be demonstrated in the three Excel videos
* The 10-page ["Torturing Excel Into Doing Statistics.pdf"](http://datajournalismcourse.net/download/TorturingExcel.php) which goes into much greater detail than the video on how to use various statistical functions and tests with Excel.
* _Python_: Using the Pandas library, you can explore your dataset, looking at summary statistics - count, median, mean, percentiles, standard deviation etc. - for each column. Next you can look into how to sort, filter, sum and count values in columns. Finally you can group data, creating (for those familiar with Excel) pivot tables, using the Pandas library.

## (4) VISUALISING DATA

Data visualisation is the graphical display of abstract information for two purposes: sense-making (also called data analysis) and communication. One of the great strengths of data visualisation is our ability to process visual information much more rapidly than verbal information.

### Human Perception

Here are a few of the principles that can inform our data visualisation efforts:

* _Proximity_ - Objects that are close together are perceived as a group.
* _Similarity_ - Objects that share similar attributes (e.g., colour or shape) are perceived as a group.
* _Enclosure_ - Objects that appear to have a boundary around them (e.g., formed by a line or area of common colour) are perceived as a group.
* _Closure_ - Open structures are perceived as closed, complete, and regular whenever there is a way that they can be reasonably interpreted as such.
* _Continuity_ - Objects that are aligned together or appear to be a continuation of one another are perceived as a group.
* _Connection_ - Objects that are connected (e.g., by a line) are perceived as a group.

### Geo and mapping

A lot of data sets media are reporting on today also have the geographical component and therefore lend themselves well to mapping. The concept of mapping data was first pioneered by the data scientist John Snow who in the 1850s mapped Cholera cases and deaths onto a map, quickly uncovering the source of the disease.

* In order work with maps it is important to convert addresses to lat/long geocodes.
* _[Quantum GIS](https://qgis.org/en/site/)_ - is an open source tool for producing basic static maps.
* _[Carto](https://carto.com/)_ - is an online tool for making interactive maps with filters, counters, hover over effects; or animated maps, which change over time, to reflect time passing.
* _[Flourish studio](https://flourish.studio/)_
* _[Google Maps](https://www.google.com/maps/@46.5597339,6.7306405,15z)_
* _[Google My Maps](https://www.google.com/maps/about/mymaps/)_
* _[Google Earth Pro](https://www.google.com/earth/versions/#earth-pro)_
* _[Google Earth Studio](https://www.google.com/earth/studio/)_

### Charting
* _[Chartblocks](https://www.chartblocks.com/en/) - is a static chart generator.
* _[RAWGraphs](https://rawgraphs.io/) - produces more exotic, less common visualisations and the outputs are also vector graphics
* _[Data GIF maker](https://datagifmaker.withgoogle.com/)
* _[Flourish studio](https://flourish.studio/)_
* _[Data wrapper](https://www.datawrapper.de/)_
* _[Tableau](https://www.tableau.com/)

## (5) GOING VIRAL

* Optimizely: Is a tool that can be used A/B testing variants, such as headlines, images etc.
* Google Alerts: Use google alerts to inform you if content has achieve an unacceptably low engagement, so that you can troubleshoot the content.
* Build a social media army of influencers who can re-shares your content.
