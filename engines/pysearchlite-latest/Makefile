clean:
	rm -fr idx
	rm -f pysearchlite

compile: pysearchlite

index: idx

serve: compile
	@python -m pysearchlite.commands.do_query idx

pysearchlite:
	@echo "\n\n\n--- Copy pysearchlite ---"
	@rm -f pysearchlite
	@ln -s ../../../pysearchlite/pysearchlite .

idx: compile
	@echo "\n\n\n---- Indexing pysearchlite ----"
	python -m pysearchlite.commands.build_index "$@" < ${CORPUS}
