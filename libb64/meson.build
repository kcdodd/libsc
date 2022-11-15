sources = [
  'b64dec.c',
  'b64enc.c',
  'cencode.c',
  'cdecode.c' ]

libb64_static_lib = static_library(
  # NOTE: only built to statically link the executable
  'libb64',
  sources,
  install : false )

libb64_dep = declare_dependency(
  include_directories : libb64_inc,
  link_with : libb64_static_lib )
