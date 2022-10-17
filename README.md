# man2ebook

A tool to convert all installed man pages to a simple ebook with contents in the head.

Maybe this could be only a small shell script but if not I will use Python.

## Why man pages as ebook?

Because I want to read them comfortable on my ebook when traveling. Not more... ;)

## Helpful libraries and tools

- https://pandoc.org/ - Haskell and then maybe make use of https://pypi.org/project/pandocfilters/, 
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
