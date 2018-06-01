project('teensy-wire', 'cpp', 'c',
    version : '1.0')

assert(meson.is_cross_build(), 'Teensy projects can only be built in a cross build environment.')

teensy_core_dep = dependency('teensy-core',
    fallback: ['teensy-core', 'teensy_core_dep'])

teensy_wire_cppflags = [
    #too many warnings due to non virtual dtor in teesy-core
    '-Wno-non-virtual-dtor',
    ]

teensy_wire_incdir = include_directories('.')
teensy_wire_src = [
    'i2c_t3.cpp',
  ]

teensy_wire = static_library('teensy-wire', teensy_wire_src,
    include_directories : teensy_wire_incdir,
    cpp_args : teensy_wire_cppflags,
    dependencies : [teensy_core_dep])

teensy_wire_dep = declare_dependency(
    link_with : teensy_wire,
    include_directories : teensy_wire_incdir,
    )
