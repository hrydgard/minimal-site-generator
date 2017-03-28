# Make sure to register your PHP files in PAGES
# and your templates in TEMPLATES.

PAGES=\
	./index.html \
	./about.html \
	./history.html

TEMPLATES=\
	header.inc \
	footer.inc

PREFIX=../pub

REALPREFIX=$(realpath $(PREFIX))

$(REALPREFIX)/%.html : %.php $(TEMPLATES)
	@mkdir -p `dirname $@`
	@cd `dirname $<`; php `basename $<` > $@

default: $(addprefix $(REALPREFIX)/,$(PAGES)) staticstuff

staticstuff:
	@rsync -auvi --exclude='*.php' --exclude='*.inc' --exclude='Makefile' ./ $(REALPREFIX)/

clean:
	@rm -r $(REALPREFIX)/*
	@rm -r $(REALPREFIX)/*
