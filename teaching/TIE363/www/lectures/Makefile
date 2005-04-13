#RST2HTML=/usr/share/python-docutils/rst2html.py
RST2HTML=rst2html

RST = $(shell find . -name '*.rst' -print | sed 's/.rst//;')

all: rst

rst:
	for f in $(RST); do echo Compile $$f.rst; $(RST2HTML) $$f.rst $$f.html; done
