sources = [
  'dictionary.c',
  'inistring.c',
  'iniparser.c' ]

inc = include_directories('.')

iniparser_static_lib = static_library(
  # NOTE: only built to statically link the executable
  'iniparser',
  sources,
  include_directories : sc_inc,
  install : false )

iniparser_dep = declare_dependency(
  include_directories : iniparser_inc,
  link_with : iniparser_static_lib )
