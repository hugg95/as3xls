## Introduction ##

Some time ago I was working on a little project for which I wanted to read and write Excel files in Flex. I Googled hither and yon but sadly I could only find a sample someone tossed out there sans code. So, I put together a little package to read and write Excel files. So far it supports reading text, numbers, formulas, and dates from Excel version 2.x-2003 and writing text, numbers, and dates. Formulas also update to reflect changes in cells they reference.

The API is intended to be straightforward and easy to use. There are some samples to play with and the obligatory ASdocs.