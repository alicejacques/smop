# for py3: make PYTHON=python3 CYTHON="cython -3" V=3.4
VPATH  = $(shell find $(SCRIPTS) -type d)
OCTAVE = /home/lei/octave-4.0.2
SCRIPTS= $(OCTAVE)/scripts
PYFILES= $(sort $(subst .m,.py,$(notdir $(MFILES) )))
MFILES = $(shell find $(SCRIPTS) -name \*.m -type f)
CYTHON = cython
PYTHON = python
CAT    = cat
XFILES = -x white.m,summer.m,spring.m,rainbow.m,prism.m,pink.m,ocean.m,lines.m,jet.m
FLAGS  = 
SMOP   = $(PYTHON) ../main.py

V = 2.7

all: $(PYFILES)
	grep Autogen libscripts.py | wc -l

clean:
	rm -f libscripts.py *.pyc *.py

%.py: %.m
	$(SMOP) $^ $(FLAGS) $(XFILES)
	($(PYTHON) $@ && $(CAT) $@ >> libscripts.py)


