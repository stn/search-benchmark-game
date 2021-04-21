
clean:
	rm -fr idx
	rm -fr target

compile: target/release/build_index target/release/do_query

index: idx

serve: target/release/do_query
	@target/release/do_query idx

target/release/%:
	@rustup override set 1.51.0
	@echo "\n\n\n--- Building tantivy's binary ---"
	@cargo build --release --bin $(notdir $@)

idx: target/release/build_index
	@echo "\n\n\n---- Indexing tantivy ----"
	@mkdir -p idx
	export RUST_LOG=info && target/release/build_index "$@" < ${CORPUS}
