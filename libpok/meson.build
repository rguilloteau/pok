project('libpok', 'c')
inc = include_directories('include')
depl = 'deployment.h'

c_flags = ['-m32', '-nostdinc', '-Wall', '-Wno-builtin-declaration-mismatch', '-Wuninitialized', '-nostdlib']
add_project_arguments(c_flags, language : 'c')

add_project_arguments('-DPOK_ARCH_X86', language : 'c')

src=[]

subdir('arch')
subdir('arinc653')
subdir('core')
subdir('drivers')
subdir('libc')
subdir('libm')
subdir('middleware')
subdir('protocols')

shared_library(
    'pok',
    c_args: ['-include', depl],
    include_directories : inc,
    sources : src
)