# Copyright © 2017 Intel Corporation

# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:

# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.

# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

inc_util = include_directories('.')

subdir('xmlpool')

files_mesa_util = files(
  'bitscan.c',
  'build_id.c',
  'crc32.c',
  'debug.c',
  'disk_cache.c',
  'half_float.c',
  'hash_table.c',
  'mesa-sha1.c',
  'os_time.c',
  'sha1/sha1.c',
  'ralloc.c',
  'rand_xor.c',
  'register_allocate.c',
  'rgtc.c',
  'set.c',
  'slab.c',
  'string_buffer.c',
  'strtod.c',
  'u_atomic.c',
  'u_queue.c',
  'u_vector.c',
)

install_data('drirc', install_dir : get_option('sysconfdir'))

files_xmlconfig = files(
  'xmlconfig.c',
)

format_srgb = custom_target(
  'format_srgb',
  input : ['format_srgb.py'],
  output : 'format_srgb.c',
  command : [prog_python2, '@INPUT0@'],
  capture : true,
)

libmesa_util = static_library(
  'mesa_util',
  [files_mesa_util, format_srgb],
  include_directories : inc_common,
  dependencies : [dep_zlib, dep_clock, dep_thread, dep_atomic],
  c_args : [c_msvc_compat_args, c_vis_args],
  build_by_default : false
)

libxmlconfig = static_library(
  'xmlconfig',
  files_xmlconfig,
  include_directories : inc_common,
  dependencies : [dep_expat, dep_m],
  c_args : [
    c_msvc_compat_args, c_vis_args,
    '-DSYSCONFDIR="@0@"'.format(
      join_paths(get_option('prefix'), get_option('sysconfdir'))
    ),
  ],
  build_by_default : false,
)

if with_tests
  test(
    'u_atomic',
    executable(
      'u_atomic_test',
      files('u_atomic_test.c'),
      include_directories : inc_common,
      link_with : libmesa_util,
      c_args : [c_msvc_compat_args],
    )
  )

  test(
    'roundeven',
    executable(
      'roundeven_test',
      files('roundeven_test.c'),
      include_directories : inc_common,
      c_args : [c_msvc_compat_args],
      dependencies : [dep_m],
    )
  )

  test(
    'mesa-sha1',
    executable(
      'mesa-sha1_test',
      files('mesa-sha1_test.c'),
      include_directories : inc_common,
      link_with : libmesa_util,
      c_args : [c_msvc_compat_args],
    )
  )

  subdir('tests/hash_table')
  subdir('tests/string_buffer')
endif
