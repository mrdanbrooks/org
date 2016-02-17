
org
    Display current directory information, along with sub directories

org doc
    Same as 'org', but creates a README.org file in the directory 

org initdir 
    Creates an .org file in the current directory

org check
    Checks the current directory meets rules

org --tree
    Displays the organization tree with current directory as root

org --depth 2
    Display current directory information, along with sub directories
    recursively to a limit depth of 2.

org --tree --depth 2
    Displays the organization tree with current directory as root.
    Limits the recursion depth to 2

org check --depth 2
    Checks the current directory meets rules, and recuses a depth of 2




$ org
-------------------
DESCRIPTION
    This directory should contain some files etc...

RULES
    No directories.

/Movies
    This is where the movies should go.

/Music
    This is where the music should go.

/Books
    This is where the books should go.
--------------------
DESCRIPTION
    This directory should contain some files etc...

RULES
    No directories.

VIOLATIONS
    /Stuff - not listed in acceptabed directories in .org file
    things.txt - no text files allowed.

/Movies
    This is where the movies should go.

/Music
    This is where the music should go.

/Books
    This is where the books should go.
--------------------

$ org tree

* Movies
  * Action
  * Animated
* Music
* Pictures
  * Photos
    * 2005
    * 2006
  * Backgrounds
* Books
  * Audiobooks
  * pdfs

--------------------

$ org --depth 2

DESCRIPTION
    This directory should contain some files etc...

RULES
    No directories.

/Movies
    This is where the movies should go.

/Movies/Action
    This is where action movies go

/Movies/Animated
    This is where animated movies go 

/Music
    This is where the music should go.

/Books
    This is where the books should go.


------------------------------

$ org tree --depth 2

* Movies
  * Action
  * Animated
* Music
* Pictures
  * Photos
    * 2005
    * 2006
  * Backgrounds
* Books
  * Audiobooks
  * pdfs

--------------------


TODO
====
- execute a script to determine if rules are broken in addition to directories / files checking
