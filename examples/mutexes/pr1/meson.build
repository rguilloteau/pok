project('simple', 'c')

libpok_folder = 'libpok'
depl = '../deployment.h'

add_project_arguments('-DPOK_ARCH_X86', language : 'c')

pok_path = '../../../'
run_command('ln', '-s', pok_path+libpok_folder, libpok_folder)

inc = include_directories(libpok_folder+'/include')

src_part = ['main.c', 'activity.c']

subdir(libpok_folder)

executable('myexe',
    sources : src_part,
    link_with : libpok,
    include_directories : inc,
    c_args: ['-include', depl],
    link_args : ['-Wl,-m,elf_i386', '-T', '/home/rguilloteau/stage/pok/misc/ldscripts/x86/x86-qemu/partition.lds']
)
