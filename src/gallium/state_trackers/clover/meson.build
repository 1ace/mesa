# Copyright © 2017-2018 Intel Corporation

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

clover_cpp_args = []
clover_incs = [inc_include, inc_src, inc_gallium, inc_gallium_aux]

if with_opencl_icd
  clover_cpp_args += '-DHAVE_CLOVER_ICD'
endif

libcltgsi = static_library(
  'cltgsi',
  files('tgsi/compiler.cpp'),
  include_directories : clover_incs,
  cpp_args : [cpp_vis_args],
)

libclllvm = static_library(
  'clllvm',
  files(
    'llvm/codegen/bitcode.cpp',
    'llvm/codegen/common.cpp',
    'llvm/codegen/native.cpp',
    'llvm/invocation.cpp',
  ),
  include_directories : clover_incs,
  cpp_args : [
    cpp_vis_args,
    '-DLIBCLC_INCLUDEDIR="@0@/"'.format(dep_clc.get_pkgconfig_variable('includedir')),
    '-DLIBCLC_LIBEXECDIR="@0@/"'.format(dep_clc.get_pkgconfig_variable('libexecdir')),
    '-DCLANG_RESOURCE_DIR="@0@"'.format(join_paths(
      dep_llvm.get_configtool_variable('libdir'), 'clang',
      dep_llvm.get_configtool_variable('version'), 'include',
    )),
  ],
  dependencies : [dep_llvm, dep_elf],
)

clover_files = files(
  'api/context.cpp',
  'api/device.cpp',
  'api/dispatch.cpp',
  'api/event.cpp',
  'api/interop.cpp',
  'api/kernel.cpp',
  'api/memory.cpp',
  'api/platform.cpp',
  'api/program.cpp',
  'api/queue.cpp',
  'api/sampler.cpp',
  'api/transfer.cpp',
  'core/context.cpp',
  'core/device.cpp',
  'core/event.cpp',
  'core/format.cpp',
  'core/kernel.cpp',
  'core/memory.cpp',
  'core/module.cpp',
  'core/platform.cpp',
  'core/program.cpp',
  'core/queue.cpp',
  'core/resource.cpp',
  'core/sampler.cpp',
  'core/timestamp.cpp',
)

libclover = static_library(
  'clover',
  clover_files,
  include_directories : clover_incs,
  cpp_args : [clover_cpp_args, cpp_vis_args],
  link_with : [libcltgsi, libclllvm],
)
