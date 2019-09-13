project('x16-emulator', 'c',
  version : '0.1',
  default_options : ['warning_level=3'])

sdl_dep = dependency('sdl2', fallback: ['sdl2', 'sdl2_dep'])
thread_dep = dependency('threads')
cc = meson.get_compiler('c')
libm = cc.find_library('libm', required: false)
dependencies = [sdl_dep, thread_dep, libm]

includes = include_directories('.', './cpu')

sources = [
  'cpu/fake6502.c',
  'debugger.c',
  'disasm.c',
  'loadsave.c',
  'main.c',
  'memory.c',
  'ps2.c',
  'sdcard.c',
  'via.c',
  'video.c',
]

executable('x16emu',
          sources,
          include_directories: includes,
          dependencies: dependencies,
          install : true)
