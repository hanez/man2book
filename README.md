# man2book

man2book is a tool to create a custom book of installed man pages or a
selection of manpage sections and / or pages.

**After only one day of development the first stable code is here. At all it took me about two 
days thinking about to start coding my idea... Here is the result!**

**\o/**

Hope this is useful to someone. Have fun!

## FAQ

### Why man pages as a book?

Because I want to read them comfortable on my ebook reader when traveling but all or some selected 
man pages in one or multiple books. Not more... ;)

### Which manpage sections are supported by man2book?

Currently, the following manpage sections are supported, but it can support other custom sections:

1. User commands; man-pages includes a small number of Section 1 pages that document programs 
supplied by the GNU C library.
2. System calls documents the system calls provided by the Linux kernel.
3. Library functions documents the functions provided by the standard C library.
4. Devices documents details of various devices, most of which reside in /dev.
5. Files describes various file formats and filesystems, and includes proc(5), which documents 
the /proc file system.
7. Overviews, conventions, and miscellaneous.
8. Superuser and system administration commands; man-pages includes a small number of Section 8 
pages that document programs supplied by the GNU C library.

Source: [https://www.kernel.org/doc/man-pages/](https://www.kernel.org/doc/man-pages/)

## Helpful libraries and tools

- https://pandoc.org/ - Haskell - Then maybe make use of https://pypi.org/project/pandocfilters/,
  https://pypi.org/project/pypandoc/ or https://pypi.org/project/pandoc/.
  (very mature features for document conversion like direct manpage input and epub output,
  but I don't know much about pandoc, so I need to discover this.)
- ~~https://www.gnu.org/software/groff/
  (man -Thtml df > df.html)~~
- ~~https://linux.die.net/man/1/man2html
  (is nice because it must not generate html, head and body)~~
- ~~https://pypi.org/project/epubmaker/ - Python
  (maybe nice but unmaintained)~~
- ~~https://docutils.sourceforge.io/ - Python
  (as I can see now it only converts from .rst files.)~~
- ~~https://github.com/hanez/aov-html2epub - Bash~~

## Workflow

1. ~~Read manpage sections~~
2. ~~Create HTML file for each manpage in each section~~
3. ~~Read and store title(metadata) for in each file~~
4. ~~Remove all unneeded stuff like html, head and body in each file~~
5. ~~Create TOC for the entire ebook~~
6. Create a header HTML file for the ebook containing the head tag
7. Merge toc and content of all files for preparing the ebook
8. Merge the header file with the prepared ebook while inserting html and body
   tags which should result in a valid HTML file
9. Create ebook from the resulting HTML file using Pandoc

## Future

When the above steps are done, and we could build a complete book there are some
feature ides:

- Some kind of template for the book including a cover.
- Image support for the cover.
- Maybe a footer for pages and the complete book.
- Page numbers on all pages after the table of contents. Like in real books.
- Support all output formats of Pandoc. This should be easy since I do not do any
  special here. Pandoc is my base converter /generator.
- Maybe support for other converters / generators.
- Links to other man pages as mentioned in the footer of all man pages, e.g.: pam(8).
  But only if available in the current book.
- Maybe a progress bar instead of printing for every file being processed 
(https://www.geeksforgeeks.org/progress-bars-in-python/).

## Bugs

- Includes in man pages does not work. Need to discover this, but I do not 
know how to solve this and if Pandoc supports that (maybe when setting some include 
path somewhere?).

## Links

- [The Linux man-pages project](https://www.kernel.org/doc/man-pages/) - I found this 
project after researching a little for my idea and it inspired me a lot to start my project.
