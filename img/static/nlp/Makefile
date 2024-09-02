# !/usr/bin/env make -f

all: slide.pdf

clean:
	rm tmp/*.pdf.part *.pdf

slide.pdf: $(patsubst %.svg,tmp/%.pdf.part,$(shell ls *.svg | sort))
	pdftk $^ cat output $@

tmp/%.pdf.part: %.svg tmp
	inkscape -A $@ $<

tmp:
	mkdir tmp
