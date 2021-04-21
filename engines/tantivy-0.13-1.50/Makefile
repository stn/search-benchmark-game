clean:
	rm -fr target

compile: target/release/build_index target/release/do_query

index:

serve: target/release/do_query
	@target/release/do_query ../tantivy-0.13-1.51/idx

target/release/%:
	@rustup override set 1.50.0
	@echo "\n\n\n--- Building tantivy's binary ---"
	@cargo build --release --bin $(notdir $@)

idx: target/release/build_index
	echo "unsupported"
