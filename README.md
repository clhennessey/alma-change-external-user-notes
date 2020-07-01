# alma-change-external-user-notes
<b>Convert Alma user notes from external to internal</b>

Presented at eCAUG conference, Thursday, July 2, 2020 (will link to recording and slides when they are available)
https://sites.google.com/view/ecaug/home

Alma user notes cannot be deleted if they are marked as "external". 
This is a quick Python program to change the notes from external to internal so you can delete or change them. 
Change "strings_to_search" variable to whatever strings you want to match on in the user note text,
and those particular external notes will be turned into internal notes.
Replace api_key in the config.ini with your API key that allows: User-Production-Read/Write.

Known errors: if you replace a user record that has associated roles that did not require 
a service unit before but need one now, you will get errors when re-writing the user record to Alma.
Edit the user record roles in Alma until the user record allows you to re-rewrite it. 
Good candidates to check for a missing service unit:

This was part of a longer program that does many things to an individual user record, hence the overkill on the
structure of the program. 

This program is based on this code presented at ELUNA Developer's Day Workshop by Jeremy Hobbs,
linked here: https://github.com/MrJeremyHobbs/ELUNA-2019-Dev-Days-Alma-Course 

Requirements: Python 3.x, modules: <i>requests, xmltodict</i>

Questions, comments, changes?
Contact Christina Hennessey, Systems Librarian at California State University, Northridge
christina.hennessey@csun.edu
