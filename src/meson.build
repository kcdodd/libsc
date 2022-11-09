
#+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
sc_lib_sources = [
  'sc.c',
  'sc_allgather.c',
  'sc_amr.c',
  'sc_avl.c',
  'sc_blas.c',
  'sc_bspline.c',
  'sc_containers.c',
  'sc_dmatrix.c',
  'sc_flops.c',
  'sc_functions.c',
  'sc_getopt.c',
  'sc_getopt1.c',
  'sc_io.c',
  'sc_keyvalue.c',
  'sc_lapack.c',
  'sc_mpi.c',
  'sc_notify.c',
  'sc_obstack.c',
  'sc_options.c',
  'sc_polynom.c',
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
  'sc_warp.c' ]

#+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
config_file = configure_file(
  input: 'sc_config.h.in',
  output: 'sc_config.h',
  configuration : {
    'package' : meson.project_name(),
    'version' : meson.project_version(),
    'version_major' : meson.project_version().split('.')[0],
    'version_minor' : meson.project_version().split('.')[1], 
    'version_revision' : meson.project_version().split('.')[2],
    'cc' : '',
    'cflags' : '',
    'fflags' : '',
    'cpp' : '', 
    'cppflags' : '',
    'ldflags' : '',
    'libs' : '' })

#+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
install_subdir(
  '.',
  install_dir : get_option('includedir') + '/sc',
  exclude_files : sc_lib_sources + [ 'meson.build' ] )

sc_shared_lib = shared_library(
  # NOTE: the 'public' library, and what is linked with the python warappers
  'sc',
  sc_lib_sources,
  dependencies : m_deps + mpi_deps,
  include_directories : sc_inc,
  c_args : c_args,
  link_args : link_args,
  install: true )