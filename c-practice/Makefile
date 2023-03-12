



build_dir := ./build

target_file := main

src_file := $(target_file).c
obj_file := $(build_dir)/$(target_file).o
asm_file := $(build_dir)/$(target_file).s
pre_processed_file := $(build_dir)/$(target_file)_preprocessed.c


$(target_file): $(obj_file)
	ld $(obj_file) -o $(target_file) -lSystem -syslibroot `xcrun -sdk macosx --show-sdk-path` -e _start -arch arm64 

$(obj_file): $(asm_file)
	as $(asm_file) -o $(obj_file) -arch arm64

$(asm_file): $(pre_processed_file)
	gcc -S $(pre_processed_file) -o $(asm_file)

$(pre_processed_file): $(src_file) $(build_dir)
	gcc -E $(src_file) -o $(pre_processed_file)

$(build_dir):
	mkdir $(build_dir)


.PHONY: clean

clean:
	rm -rf $(build_dir)

