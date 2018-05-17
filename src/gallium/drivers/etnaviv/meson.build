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

files_etnaviv = files(
  'etnaviv_asm.c',
  'etnaviv_blend.c',
  'etnaviv_blt.c',
  'etnaviv_clear_blit.c',
  'etnaviv_compiler.c',
  'etnaviv_context.c',
  'etnaviv_disasm.c',
  'etnaviv_emit.c',
  'etnaviv_fence.c',
  'etnaviv_format.c',
  'etnaviv_query.c',
  'etnaviv_query_hw.c',
  'etnaviv_query_sw.c',
  'etnaviv_query_pm.c',
  'etnaviv_rasterizer.c',
  'etnaviv_resource.c',
  'etnaviv_rs.c',
  'etnaviv_screen.c',
  'etnaviv_shader.c',
  'etnaviv_state.c',
  'etnaviv_surface.c',
  'etnaviv_texture.c',
  'etnaviv_texture_state.c',
  'etnaviv_tiling.c',
  'etnaviv_transfer.c',
  'etnaviv_uniforms.c',
  'etnaviv_zsa.c',
)

libetnaviv = static_library(
  'etnaviv',
  files_etnaviv,
  c_args : [c_vis_args],
  include_directories : [inc_include, inc_src, inc_gallium, inc_gallium_aux],
  dependencies : dep_libdrm_etnaviv,
)

etnaviv_compiler = executable(
  'etnaviv_compiler',
  'etnaviv_compiler_cmdline.c',
  include_directories : [inc_include, inc_src, inc_gallium, inc_gallium_aux],
  link_with : [libmesa_util, libgallium, libetnaviv],
  dependencies : [dep_libdrm_etnaviv],
  build_by_default : false,
)

driver_etnaviv = declare_dependency(
  compile_args : '-DGALLIUM_ETNAVIV',
  link_with : [libetnaviv, libetnavivdrm],
)
