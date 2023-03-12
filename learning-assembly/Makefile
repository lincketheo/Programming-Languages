
mac_target := hello_mac64
mac_src := $(mac_target).asm
mac_obj := $(mac_target).o

$(mac_target): $(mac_obj)
	ld $(mac_obj)

$(mac_obj): $(mac_src)
	nasm -farm64 $(mac_src)

.PHONY: clean
clean:
	rm -f $(mac_obj) $(mac_target)

