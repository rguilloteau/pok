libpok_folder = 'libpok'
depl = '../deployment.h'

pok_path = '../../../'
run_command('ln', '-s', pok_path+libpok_folder, libpok_folder)

inc = include_directories(libpok_folder+'/include')

src_part = ['main.c', 'activity.c']

if not libpok_visited
    subdir(libpok_folder)
    libpok_visited = true
endif

part = executable('pr2.elf',
    sources : [src_part, src],
    include_directories : inc,
    c_args: ['-include', depl],
    link_args : ['-Wl,-m,elf_i386,-no-dynamic-linker', '-T', '/home/rguilloteau/stage/pok/misc/ldscripts/x86/x86-qemu/partition.lds']
)
