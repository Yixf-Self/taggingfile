taggingfile
==========

Cataloging files by tags (Only for *nix right now!!!)

Motivation
----------
 
I simply cataloged publication PDF files by storing them in different 
directories which stands for different categories. However some
publiction belong to several fields. It made me crazy for cataloging
them.

It's not a good practice to copy it to different directories, because it
will occupy more disk space and the modify only act for one file.

Symbolic link is the solution to disk usage and file consistency.

Details
-------

- File organization:

    - The hierarchic directories in current path countain targets files.

    - Every file in the directory would be paired with a tag file,
    for example, "a.txt" is paired with "a.txt.tag". 
    
- Tag:

    - Tag file countains tags in multline. If no tag file given
    or no tags found in tag file. The file will be categorized 
    as "Uncategorized".
    
    - Hierarchic tag is supported. e.g, "Tag 2, Important".

- This script should be excuted in same path with the directory.

- File suffix (optional) is for filter of the files.

- Directories with name of tags will be created in current path.

- The symlink use relative path. Unlinked symlinks will NOT be 
    removed every excution for security unless -renew option is specified.


Usage
-----

    Usage: taggingfile [options] [directory ...]
    
    Options:
        -h                   Print usage
        -help                Print usage and details
        -s --suffix PATTERN  File suffix for filter of the files, 
                             cases ignored. [.*]
        -p --prefix STRING   Tag directory prefix ["_TAG_"]
        -renew               Attention! It will delete and recreate the
                             directory of all tags.

Example
------

- tagging pdf files in pdfs directory

    taggingfile -d pdfs -s .pdf

- tagging all the file in current directory

    taggingfile

Copyright
--------

Copyright (c) 2014, Wei Shen (shenwei356@gmail.com)


[MIT License](https://github.com/shenwei356/taggingfile/blob/master/LICENSE)