all: byte native doc

byte: 
	dune build dummy.cma

native: 
	dune build dummy.cmxa

doc:
	dune build @doc

install: 
	dune build @install

INSTALL_DOCDIR=`opam config var doc`

opam.install: 
	opam install .
	rm -rf $(INSTALL_DOCDIR)/dummy
	cp -r _build/default/_doc/_html/ $(INSTALL_DOCDIR)/dummy

opam.remove:
	opam remove .
	rm -rf $(INSTALL_DOCDIR)/dummy

clean:
	dune clean

realclean: clean
	\rm -f *~
