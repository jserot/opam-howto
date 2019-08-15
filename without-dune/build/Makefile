PACKAGE=dummy
INSTALL_LIBDIR=`opam config var lib`
INSTALL_DOCDIR=`opam config var doc`

all: byte native doc

byte: hello.cmo
	ocamlc -a -o $(PACKAGE).cma $<

native:  hello.cmx
	ocamlopt -a -o $(PACKAGE).cmxa $<

hello.cmo: hello.cmi hello.ml 
	ocamlc -c hello.ml
hello.cmx: hello.cmi hello.ml 
	ocamlopt -c hello.ml
hello.cmi:
	ocamlc hello.mli

doc:
	\rm -f ./_doc/*
	ocamldoc -d ./_doc -html hello.mli

install: 
	rm -rf $(INSTALL_LIBDIR)/$(PACKAGE)
	ocamlfind install -destdir $(INSTALL_LIBDIR) $(PACKAGE) META *.mli *.cmi *.cmo *.cmx *.cma *.cmxa *.a
	rm -rf $(INSTALL_DOCDIR)/$(PACKAGE)
	cp -r _doc $(INSTALL_DOCDIR)/$(PACKAGE)

opam.install:
	opam install .

opam.remove:
	opam remove .
	rm -rf $(INSTALL_DOCDIR)/$(PACKAGE)

clean:
	\rm -f *.cmi *.cmo *.cmx *.cma *.cmxa *.o *.a

realclean: clean
	\rm -f *~
