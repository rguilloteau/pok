src=[]

subdir('arch')
subdir('arinc653')
subdir('core')
subdir('drivers')
subdir('libc')
subdir('libm')
subdir('middleware')
subdir('protocols')

libpok = static_library(
    'pok',
    c_args: ['-include', depl],
    include_directories : inc,
    sources : src
)