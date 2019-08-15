run: main.bc main.exe
	./main.bc
	./main.exe

main.bc:
	ocamlfind ocamlc -package dummy -linkpkg -o main.bc main.ml

main.exe:
	ocamlfind ocamlopt -package dummy -linkpkg -o main.exe main.ml

BROWSER=open -a Safari
DOCDIR=`opam config var doc`

viewdoc:
	$(BROWSER) $(DOCDIR)/dummy/index.html

clean:
	\rm -f *.cmi *.cmo *.cmx *.o
	\rm -f main.bc main.exe

realclean: clean
	\rm -f *~
