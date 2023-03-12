
target := main
src := $(target).hs

outputs := $(target).o $(target).hi $(target)

$(target): $(src)
	ghc $(src)

.PHONY: clean

clean:
	rm -f $(outputs)

