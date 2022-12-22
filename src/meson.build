
#+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
sc_lib_sources = [
  'sc.c',
  'sc_allgather.c',
  'sc_amr.c',
  'sc_avl.c',
  # 'sc_blas.c',
  # 'sc_bspline.c',
  'sc_containers.c',
  # 'sc_dmatrix.c',
  'sc_flops.c',
  'sc_functions.c',
  'sc_getopt.c',
  'sc_getopt1.c',
  'sc_io.c',
  'sc_keyvalue.c',
  # 'sc_lapack.c',
  'sc_mpi.c',
  'sc_notify.c',
  # 'sc_obstack.c',
  'sc_options.c',
  'sc_polynom.c',
  'sc_puff.c',
  'sc_random.c',
  'sc_ranges.c',
  'sc_reduce.c',
  'sc_refcount.c',
  'sc_search.c',
  'sc_shmem.c',
  'sc_sort.c',
  'sc_statistics.c',
  'sc_string.c',
  'sc_uint128.c',
  'sc_unique_counter.c',
  'sc_v4l2.c',
  # 'sc_warp.c'
  ]

#+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
config_file = configure_file(
  input: '../cmake/sc_config.h.in',
  output: 'sc_config.h',
  format: 'cmake@',
  configuration: sc_config )

#+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
install_subdir(
  '.',
  install_dir : get_option('includedir') + '/sc',
  exclude_files : sc_lib_sources + [
    'CMakeLists.txt',
    'Makefile.am',
    'meson.build' ] )

sc_shared_lib = shared_library(
  # NOTE: the 'public' library, and what is linked with the python warappers
  'sc',
  sc_lib_sources,
  dependencies : m_deps + zlib_deps + mpi_deps + iniparser_dep + libb64_dep,
  include_directories : sc_inc,
  c_args : c_args,
  link_args : link_args,
  install: true )