project('Build', 'c')

add_project_arguments('-DPOK_ARCH_X86', language : 'c')

partitions_name = ['pr1', 'pr2']
partitions = []
libpok_visited = false

foreach p : partitions_name
    subdir(p)
    partitions += part
endforeach

subdir('kernel')

executable('pok.elf',
    sources : 'sizes.c',
    include_directories : inc,
    link_with : kernel,
    link_args : ['-Wl,-m,elf_i386,-no-dynamic-linker', '-T', '/home/rguilloteau/stage/pok/misc/ldscripts/x86/x86-qemu/kernel.lds']
)

