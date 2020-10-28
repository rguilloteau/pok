project('POK kernel', 'c')
inc = include_directories('include')
depl = 'deployment.h'
tmp_h = 'tmp.h'

c_flags = ['-m32', '-nostdinc', '-Wall', '-Wno-builtin-declaration-mismatch', '-Wuninitialized', '-nostdlib']
add_project_arguments(c_flags, language : 'c')

add_project_arguments('-DPOK_ARCH_X86', language : 'c')

src_c=[]
src_asm=[]

subdir('arch')
subdir('core')
subdir('drivers')
subdir('libc')
subdir('middleware')

kernel_asm = static_library(
    'kernel_asm',
    c_args: ['-include', tmp_h],
    include_directories : inc,
    sources : src_asm
)

static_library(
    'kernel',
    c_args: ['-include', depl],
    include_directories : inc,
    sources : src_c,
    link_with : kernel_asm
)