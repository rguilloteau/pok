kernel_folder = 'kernel'
depl = '../deployment.h'

pok_path = '../../../'
run_command('ln', '-s', pok_path+kernel_folder, kernel_folder)

inc = include_directories(kernel_folder+'/include')

subdir(kernel_folder)

kernel = static_library(
    'kernel',
    c_args: ['-include', depl],
    include_directories : inc,
    sources : src,
)