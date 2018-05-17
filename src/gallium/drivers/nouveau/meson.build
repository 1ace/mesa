# Copyright © 2017 Dylan Baker

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

files_libnouveau = files(
  'nouveau_buffer.c',
  'nouveau_fence.c',
  'nouveau_heap.c',
  'nouveau_mm.c',
  'nouveau_screen.c',
  'nouveau_video.c',
  'nouveau_vp3_video_bsp.c',
  'nouveau_vp3_video.c',
  'nouveau_vp3_video_vp.c',
  'nv30/nv30_clear.c',
  'nv30/nv30_context.c',
  'nv30/nv30_draw.c',
  'nv30/nv30_format.c',
  'nv30/nv30_fragprog.c',
  'nv30/nv30_fragtex.c',
  'nv30/nv30_miptree.c',
  'nv30/nv30_push.c',
  'nv30/nv30_query.c',
  'nv30/nv30_resource.c',
  'nv30/nv30_screen.c',
  'nv30/nv30_state.c',
  'nv30/nv30_state_validate.c',
  'nv30/nv30_texture.c',
  'nv30/nv30_transfer.c',
  'nv30/nv30_vbo.c',
  'nv30/nv30_vertprog.c',
  'nv30/nv40_verttex.c',
  'nv30/nvfx_fragprog.c',
  'nv30/nvfx_vertprog.c',
  'nv50/nv50_compute.c',
  'nv50/nv50_context.c',
  'nv50/nv50_formats.c',
  'nv50/nv50_miptree.c',
  'nv50/nv50_program.c',
  'nv50/nv50_push.c',
  'nv50/nv50_query.c',
  'nv50/nv50_query_hw.c',
  'nv50/nv50_query_hw_metric.c',
  'nv50/nv50_query_hw_sm.c',
  'nv50/nv50_resource.c',
  'nv50/nv50_screen.c',
  'nv50/nv50_shader_state.c',
  'nv50/nv50_state.c',
  'nv50/nv50_state_validate.c',
  'nv50/nv50_surface.c',
  'nv50/nv50_tex.c',
  'nv50/nv50_transfer.c',
  'nv50/nv50_vbo.c',
  'nv50/nv84_video_bsp.c',
  'nv50/nv84_video.c',
  'nv50/nv84_video_vp.c',
  'nv50/nv98_video_bsp.c',
  'nv50/nv98_video.c',
  'nv50/nv98_video_ppp.c',
  'nv50/nv98_video_vp.c',
  'codegen/nv50_ir.cpp',
  'codegen/nv50_ir_bb.cpp',
  'codegen/nv50_ir_build_util.cpp',
  'codegen/nv50_ir_emit_nv50.cpp',
  'codegen/nv50_ir_from_tgsi.cpp',
  'codegen/nv50_ir_graph.cpp',
  'codegen/nv50_ir_lowering_nv50.cpp',
  'codegen/nv50_ir_peephole.cpp',
  'codegen/nv50_ir_print.cpp',
  'codegen/nv50_ir_ra.cpp',
  'codegen/nv50_ir_ssa.cpp',
  'codegen/nv50_ir_target.cpp',
  'codegen/nv50_ir_target_nv50.cpp',
  'codegen/nv50_ir_util.cpp',
  'codegen/nv50_ir_emit_gk110.cpp',
  'codegen/nv50_ir_emit_gm107.cpp',
  'codegen/nv50_ir_emit_nvc0.cpp',
  'codegen/nv50_ir_lowering_gm107.cpp',
  'codegen/nv50_ir_lowering_nvc0.cpp',
  'codegen/nv50_ir_target_gm107.cpp',
  'codegen/nv50_ir_target_nvc0.cpp',
  'nvc0/nvc0_compute.c',
  'nvc0/nvc0_context.c',
  'nvc0/nvc0_formats.c',
  'nvc0/nvc0_miptree.c',
  'nvc0/nvc0_program.c',
  'nvc0/nvc0_query.c',
  'nvc0/nvc0_query_hw.c',
  'nvc0/nvc0_query_hw_metric.c',
  'nvc0/nvc0_query_hw_sm.c',
  'nvc0/nvc0_query_sw.c',
  'nvc0/nvc0_resource.c',
  'nvc0/nvc0_screen.c',
  'nvc0/nvc0_shader_state.c',
  'nvc0/nvc0_state.c',
  'nvc0/nvc0_state_validate.c',
  'nvc0/nvc0_surface.c',
  'nvc0/nvc0_tex.c',
  'nvc0/nvc0_transfer.c',
  'nvc0/nvc0_vbo.c',
  'nvc0/nvc0_vbo_translate.c',
  'nvc0/nvc0_video_bsp.c',
  'nvc0/nvc0_video.c',
  'nvc0/nvc0_video_ppp.c',
  'nvc0/nvc0_video_vp.c',
  'nvc0/nve4_compute.c',
)

libnouveau = static_library(
  'nouveau',
  [files_libnouveau],
  include_directories : [
    inc_src, inc_include, inc_gallium, inc_gallium_aux, inc_drm_uapi
  ],
  c_args : [c_vis_args],
  cpp_args : [cpp_vis_args],
  dependencies : [dep_libdrm, dep_libdrm_nouveau],
)

nouveau_compiler = executable(
  'nouveau_compiler',
  'nouveau_compiler.c',
  include_directories : [inc_src, inc_include, inc_gallium, inc_gallium_aux],
  dependencies : [dep_libdrm, dep_libdrm_nouveau],
  link_with : [libnouveau, libgallium, libmesa_util],
  build_by_default : with_tools.contains('nouveau'),
  install : with_tools.contains('nouveau'),
)

driver_nouveau = declare_dependency(
  compile_args : '-DGALLIUM_NOUVEAU',
  link_with : [libnouveauwinsys, libnouveau],
)
