.DEFAULT_GOAL := build
.PHONY: build
build:
	bin/invert_sec_labels.py && \
	bin/invert_eg_labels.py && \
	bin/volatile.py && \
	cp -a build/tmp.md ../share/csaf-v2.1-draft.md && \
	pandoc -f gfm+definition_lists -t html build/tmp.md --columns=345  --css style/base.css --css style/skin.css --standalone -o build/tmp.html && \
	bin/toccata.py && \
	timeout 2 tidy -config etc/tidy-config.txt build/injected.html -ashtml 2>/dev/null | sed 's/<!\[CDATA\[//g; s/\]\]>//g;' > ../share/csaf-v2.1-draft.html; \
	git status
