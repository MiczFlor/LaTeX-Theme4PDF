# LaTeX-Theme4PDF
This set of LaTeX book templates is aimed at making automated PDFs easier. All variables regarding metadata, paper size, themes are saved in one seperate .tex file. The master LaTeX template will read this file and change the book accordingly (e.g. build a colophon based on available metadata).

## What is this repository for? ##

* This set of scripts is meant to make the creation of a print PDF easy, using LaTeX without having to write LaTeX.
* This is like a template abstraction for LaTeX, allowing the content to come from Booktype and LaTeX improvements to be done without touching the Booktype code.
* The set of .tex files is structured to read one config file (also .tex) and then adjust metadata, design and front matter, table of contents, etc. accordingly.
* Booktype creates this config file from the metadata it has. No other files (well, only the content itself ;) need to be created.

## What do the files and folders mean? ##
* **book_master.tex** This is the main file, like the index.html for the book. In the spirit of this project, you should NOT edit this document. Content and formatting are elsewhere to be added.
* **_content folder/** This folder is your content, your book. Dump all your content here. The main file book_master.tex expecty the following three files (they can be empty, but they must exist):
    * **_content/AAfrontmatter.tex** Containing content like the introduction BEFORE the actual page counting starts.
    * **_content/AAmainmatter.tex** This is the main content, all the chapters of the book.
    * **_content/AAbackmatter.tex** Here are e.g. the epilog or appendix information.
* **BookConfig/variables.tex** You can change this file, in fact you should. This is the file containing all the metadata for the frontmatter and relevant information about the styling (page size, theme). 
* **Assets/** Similar to a website folder structure, this folder contains all media and the like which are needed by the themes to make the book pretty. Like EPS files for the chapter styling.
* **LaTeX/** This folder contains LaTeX scripts which are used to style the book. For example:
    * **LaTeX/figure_snippet.tex** This file contains the LaTeX code which will include the images in the final PDF. You don't need to write that part of LaTeX in your _content files (see below for details on including images).
    * **LaTeX/figure_pagestyle.tex** This file contains different kinds of styling for header and footer. Which one is applied is set in the theme (more on that later).
*  **LaTeX/themes/** Here are the themes. Which theme to use for the book is specified in **BookConfig/variables.tex**. The folder name inside the themes folder is the name of the theme that needs to be added in the file **BookConfig/variables.tex**.
