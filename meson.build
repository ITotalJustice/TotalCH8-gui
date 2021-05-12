project('TotalCH8-gui', ['c'],
    version: '1.0.0',
    license : 'MIT',
    default_options: [
        # core options
        'buildtype=debug',
        'warning_level=3',
        'optimization=3',
        'strip=true',
        'c_std=c99',
    ],
)

dependencies = [
    dependency('TotalCH8'),
    dependency('sdl2'),
    dependency('args'),
]

source = files([
    'src/main.c',
])

includes = include_directories([
])

cflags = [
    # warns
    '-Wall',
    '-Wextra',
    '-Werror',
    '-Wfatal-errors',
    '-Wpedantic',
    '-Wshadow',
    '-Wdouble-promotion',
    '-Wformat=2',
    '-Wformat-overflow=2',
    '-Wformat-truncation=1',
    '-Wundef',
    '-Wmissing-include-dirs',
    '-Wstrict-aliasing=2',
    '-Walloca',
    '-Wduplicated-branches',
    '-Wduplicated-cond',
    '-Wwrite-strings',
    '-Wdate-time',
    '-Wsizeof-pointer-memaccess',
    '-Wlogical-op',
    '-Wpacked',
    '-Wredundant-decls',
    '-Wnested-externs',
    '-Winline',

    '-freg-struct-return',
    '-fno-common',

    '-Wno-unused-function',

    # these also need to be added to the linker!
    '-fsanitize=address',
    '-fsanitize=leak',
    '-fsanitize=undefined',
    '-fsanitize=pointer-compare',
    '-fsanitize=pointer-subtract',
    '-fstack-protector-all',
]

linkflags = [
    '-fsanitize=address',
    '-fsanitize=leak',
    '-fsanitize=undefined',
    '-fsanitize=pointer-compare',
    '-fsanitize=pointer-subtract',
    '-fstack-protector-all',
]

exe = executable(
    'TotalCH8-gui',
    [ source ],
    dependencies : [ dependencies ],
    install: true,
    include_directories: [ includes ],
    c_args: [ cflags ],
    link_args: [ linkflags ],
)

# scripts
run_target('cppcheck',
  command : 'scripts/cppcheck.sh')
