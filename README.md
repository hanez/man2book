# man2book

A tool to convert all installed man pages to a simple ebook or other formats with contents in the head.

Maybe this could be only a small shell script but if not I will use Python.

## Why man pages as ebook?

Because I want to read them comfortable on my ebook reader when traveling but all man pages in one book.
Not more... ;)

## Helpful libraries and tools

- https://pandoc.org/ - Haskell - Then maybe make use of https://pypi.org/project/pandocfilters/, 
  https://pypi.org/project/pypandoc/ or https://pypi.org/project/pandoc/.
  (very mature features for document conversion like direct manpage input and epub output, 
  but I don't know much about pandoc, so I need to discover this.)
- https://www.gnu.org/software/groff/
  (man -Thtml df > df.html)
- https://linux.die.net/man/1/man2html
  (is nice because it must not generate html, head and body)
- https://pypi.org/project/epubmaker/ - Python
  (maybe nice but unmaintained)
- https://docutils.sourceforge.io/ - Python
  (as I can see now it only converts from .rst files.)
- https://github.com/hanez/aov-html2epub - Bash

## Workflow

1. Read manpage sections
2. Create HTML file for each manpage in each section
3. Read and store title(metadata) for in each file
4. Remove all unneeded stuff like html, head and body in each file
5. Create TOC for the entire ebook
6. Create a header HTML file for the ebook containing the head tag
7. Merge toc and content of all files for preparing the ebook
8. Merge the header file with the prepared ebook while inserting html and body tags which should result in a valid HTML file
9. Create ebook from the resulting HTML file using Pandoc
