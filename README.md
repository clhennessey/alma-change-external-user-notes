# alma-change-external-user-notes
<b>Convert Alma user notes from external to internal</b>

Presented at eCAUG conference, Thursday, July 2, 2020. 

Slides & recording here: https://drive.google.com/drive/folders/150wsKMH5LBb9hiceCrvr_iMAuNqD7DiZ 

Conference sessions & descriptions: https://sites.google.com/view/ecaug/home

Alma user notes cannot be deleted or changed if they are marked as "external". 

This is a quick Python program to change the notes from external to internal one by one so you can delete or change them. 

Change "strings_to_search" variable to whatever strings you want to match on in the user note text,
and those particular external notes will be turned into internal notes.

Replace api_key in the config.ini with your API key that allows: User-Production-Read/Write.

Known errors: if you replace a user record that has associated roles that did not require 
a service unit before but need one now, you will get errors when re-writing the user record to Alma.
Edit the user record roles in Alma until the user record allows you to re-rewrite it. 
Good candidates to check for a missing service unit: 
Work Order Operator, Receiving Operator, Receiving Operator Limited

This was part of a longer program that does many things to an individual user record, hence the overkill on the
structure of the program. There are plenty of optional print statements in the program so you can check your
user record changes while you use the program.

If you would like a version of the program that uses an input file of IDs instead of inputting one IDs at a time, see my other program at: https://github.com/clhennessey/alma-change-external-user-notes-from-file

This program is based on this code presented at ELUNA Developer's Day Workshop by Jeremy Hobbs,
linked here: https://github.com/MrJeremyHobbs/ELUNA-2019-Dev-Days-Alma-Course 

Requirements: Python 3.x, modules: <i>requests, xmltodict</i>

Questions, comments, changes?
Contact Christina Hennessey, Systems Librarian at California State University, Northridge
christina.hennessey@csun.edu

![Program with ID entered](/program_with_ID_entered.png)

![Program complete](/program_complete.png)
