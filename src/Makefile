# @SI_Copyright@
# @SI_Copyright@

ifndef ROLL
include ../version.mk
endif

include order-$(ROLL).mk

order-$(ROLL).mk: Makefile ../version.mk $(shell find . -name version.mk)
	$(STACKBUILD)/bin/gen-order > $@


clean.order:
	-rm -f order-$(ROLL).mk

bootstrap rpm pkg clean nuke:
	@for dir in $(SRCDIRS); do			\
		(cd $$dir; $(MAKE) $@);			\
	done

dump-info::
	@for x in $(SRCDIRS); do			\
		if [ -d $$x ]; then			\
			(cd $$x; $(MAKE) $@); 		\
		fi;					\
	done
