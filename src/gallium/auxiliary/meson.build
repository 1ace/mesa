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

files_libgallium = files(
  'cso_cache/cso_cache.c',
  'cso_cache/cso_context.c',
  'cso_cache/cso_hash.c',
  'draw/draw_context.c',
  'draw/draw_fs.c',
  'draw/draw_gs.c',
  'draw/draw_pipe_aaline.c',
  'draw/draw_pipe_aapoint.c',
  'draw/draw_pipe.c',
  'draw/draw_pipe_clip.c',
  'draw/draw_pipe_cull.c',
  'draw/draw_pipe_flatshade.c',
  'draw/draw_pipe_offset.c',
  'draw/draw_pipe_pstipple.c',
  'draw/draw_pipe_stipple.c',
  'draw/draw_pipe_twoside.c',
  'draw/draw_pipe_unfilled.c',
  'draw/draw_pipe_util.c',
  'draw/draw_pipe_validate.c',
  'draw/draw_pipe_vbuf.c',
  'draw/draw_pipe_wide_line.c',
  'draw/draw_pipe_wide_point.c',
  'draw/draw_prim_assembler.c',
  'draw/draw_pt.c',
  'draw/draw_pt_emit.c',
  'draw/draw_pt_fetch.c',
  'draw/draw_pt_fetch_emit.c',
  'draw/draw_pt_fetch_shade_emit.c',
  'draw/draw_pt_fetch_shade_pipeline.c',
  'draw/draw_pt_post_vs.c',
  'draw/draw_pt_so_emit.c',
  'draw/draw_pt_util.c',
  'draw/draw_pt_vsplit.c',
  'draw/draw_vertex.c',
  'draw/draw_vs.c',
  'draw/draw_vs_exec.c',
  'draw/draw_vs_variant.c',
  'driver_ddebug/dd_context.c',
  'driver_ddebug/dd_draw.c',
  'driver_ddebug/dd_screen.c',
  'driver_noop/noop_pipe.c',
  'driver_noop/noop_state.c',
  'driver_rbug/rbug_context.c',
  'driver_rbug/rbug_core.c',
  'driver_rbug/rbug_objects.c',
  'driver_rbug/rbug_screen.c',
  'driver_trace/tr_context.c',
  'driver_trace/tr_dump.c',
  'driver_trace/tr_dump_state.c',
  'driver_trace/tr_screen.c',
  'driver_trace/tr_texture.c',
  'hud/font.c',
  'hud/hud_context.c',
  'hud/hud_cpu.c',
  'hud/hud_nic.c',
  'hud/hud_cpufreq.c',
  'hud/hud_diskstat.c',
  'hud/hud_sensors_temp.c',
  'hud/hud_driver_query.c',
  'hud/hud_fps.c',
  'indices/u_primconvert.c',
  'os/os_misc.c',
  'os/os_process.c',
  'pipebuffer/pb_buffer_fenced.c',
  'pipebuffer/pb_buffer_malloc.c',
  'pipebuffer/pb_bufmgr_alt.c',
  'pipebuffer/pb_bufmgr_cache.c',
  'pipebuffer/pb_bufmgr_debug.c',
  'pipebuffer/pb_bufmgr_mm.c',
  'pipebuffer/pb_bufmgr_ondemand.c',
  'pipebuffer/pb_bufmgr_pool.c',
  'pipebuffer/pb_bufmgr_slab.c',
  'pipebuffer/pb_cache.c',
  'pipebuffer/pb_slab.c',
  'pipebuffer/pb_validate.c',
  'postprocess/pp_celshade.c',
  'postprocess/pp_colors.c',
  'postprocess/pp_init.c',
  'postprocess/pp_mlaa.c',
  'postprocess/pp_program.c',
  'postprocess/pp_run.c',
  'rbug/rbug_connection.c',
  'rbug/rbug_context.c',
  'rbug/rbug_core.c',
  'rbug/rbug_demarshal.c',
  'rbug/rbug_shader.c',
  'rbug/rbug_texture.c',
  'rtasm/rtasm_cpu.c',
  'rtasm/rtasm_execmem.c',
  'rtasm/rtasm_x86sse.c',
  'tgsi/tgsi_aa_point.c',
  'tgsi/tgsi_build.c',
  'tgsi/tgsi_dump.c',
  'tgsi/tgsi_exec.c',
  'tgsi/tgsi_emulate.c',
  'tgsi/tgsi_from_mesa.c',
  'tgsi/tgsi_info.c',
  'tgsi/tgsi_iterate.c',
  'tgsi/tgsi_lowering.c',
  'tgsi/tgsi_parse.c',
  'tgsi/tgsi_point_sprite.c',
  'tgsi/tgsi_sanity.c',
  'tgsi/tgsi_scan.c',
  'tgsi/tgsi_strings.c',
  'tgsi/tgsi_text.c',
  'tgsi/tgsi_transform.c',
  'tgsi/tgsi_two_side.c',
  'tgsi/tgsi_ureg.c',
  'tgsi/tgsi_util.c',
  'translate/translate.c',
  'translate/translate_cache.c',
  'translate/translate_generic.c',
  'translate/translate_sse.c',
  'util/u_async_debug.c',
  'util/u_bitmask.c',
  'util/u_blit.c',
  'util/u_blitter.c',
  'util/u_cache.c',
  'util/u_cpu_detect.c',
  'util/u_debug.c',
  'util/u_debug_describe.c',
  'util/u_debug_flush.c',
  'util/u_debug_image.c',
  'util/u_debug_memory.c',
  'util/u_debug_refcnt.c',
  'util/u_debug_stack.c',
  'util/u_debug_symbol.c',
  'util/u_dl.c',
  'util/u_draw.c',
  'util/u_draw_quad.c',
  'util/u_dump_defines.c',
  'util/u_dump_state.c',
  'util/u_format.c',
  'util/u_format_etc.c',
  'util/u_format_latc.c',
  'util/u_format_other.c',
  'util/u_format_rgtc.c',
  'util/u_format_s3tc.c',
  'util/u_format_tests.c',
  'util/u_format_yuv.c',
  'util/u_format_zs.c',
  'util/u_framebuffer.c',
  'util/u_gen_mipmap.c',
  'util/u_handle_table.c',
  'util/u_hash_table.c',
  'util/u_helpers.c',
  'util/u_idalloc.c',
  'util/u_index_modify.c',
  'util/u_linear.c',
  'util/u_log.c',
  'util/u_math.c',
  'util/u_mm.c',
  'util/u_network.c',
  'util/u_prim_restart.c',
  'util/u_pstipple.c',
  'util/u_resource.c',
  'util/u_ringbuffer.c',
  'util/u_sampler.c',
  'util/u_simple_shaders.c',
  'util/u_suballoc.c',
  'util/u_surface.c',
  'util/u_surfaces.c',
  'util/u_tests.c',
  'util/u_texture.c',
  'util/u_tile.c',
  'util/u_transfer.c',
  'util/u_transfer_helper.c',
  'util/u_threaded_context.c',
  'util/u_upload_mgr.c',
  'util/u_vbuf.c',
  'nir/tgsi_to_nir.c',
)

if dep_libdrm.found()
  files_libgallium += files(
    'renderonly/renderonly.c',
  )
endif

if with_llvm
  files_libgallium += files(
    'gallivm/lp_bld_arit.c',
    'gallivm/lp_bld_arit_overflow.c',
    'gallivm/lp_bld_assert.c',
    'gallivm/lp_bld_bitarit.c',
    'gallivm/lp_bld_const.c',
    'gallivm/lp_bld_conv.c',
    'gallivm/lp_bld_debug.cpp',
    'gallivm/lp_bld_flow.c',
    'gallivm/lp_bld_format_aos_array.c',
    'gallivm/lp_bld_format_aos.c',
    'gallivm/lp_bld_format_cached.c',
    'gallivm/lp_bld_format_float.c',
    'gallivm/lp_bld_format.c',
    'gallivm/lp_bld_format_soa.c',
    'gallivm/lp_bld_format_srgb.c',
    'gallivm/lp_bld_format_yuv.c',
    'gallivm/lp_bld_gather.c',
    'gallivm/lp_bld_init.c',
    'gallivm/lp_bld_intr.c',
    'gallivm/lp_bld_logic.c',
    'gallivm/lp_bld_misc.cpp',
    'gallivm/lp_bld_pack.c',
    'gallivm/lp_bld_printf.c',
    'gallivm/lp_bld_quad.c',
    'gallivm/lp_bld_sample_aos.c',
    'gallivm/lp_bld_sample.c',
    'gallivm/lp_bld_sample_soa.c',
    'gallivm/lp_bld_struct.c',
    'gallivm/lp_bld_swizzle.c',
    'gallivm/lp_bld_tgsi_action.c',
    'gallivm/lp_bld_tgsi_aos.c',
    'gallivm/lp_bld_tgsi.c',
    'gallivm/lp_bld_tgsi_info.c',
    'gallivm/lp_bld_tgsi_soa.c',
    'gallivm/lp_bld_type.c',
    'draw/draw_llvm.c',
    'draw/draw_llvm_sample.c',
    'draw/draw_pt_fetch_shade_pipeline_llvm.c',
    'draw/draw_vs_llvm.c',
  )
endif

files_libgalliumvl = files(
  'vl/vl_bicubic_filter.c',
  'vl/vl_compositor.c',
  'vl/vl_csc.c',
  'vl/vl_decoder.c',
  'vl/vl_deint_filter.c',
  'vl/vl_idct.c',
  'vl/vl_matrix_filter.c',
  'vl/vl_mc.c',
  'vl/vl_median_filter.c',
  'vl/vl_mpeg12_bitstream.c',
  'vl/vl_mpeg12_decoder.c',
  'vl/vl_vertex_buffers.c',
  'vl/vl_video_buffer.c',
  'vl/vl_zscan.c',
)

vlwinsys_deps = []
files_libgalliumvlwinsys = []
if with_dri2
  files_libgalliumvlwinsys += files('vl/vl_winsys_dri.c')
  if with_dri3
    vlwinsys_deps += [
      dep_xcb_sync, dep_xcb_present, dep_xshmfence, dep_xcb_xfixes,
      dep_xcb_dri3, 
    ]
    files_libgalliumvlwinsys += files('vl/vl_winsys_dri3.c')
  endif
endif
if with_platform_drm
  files_libgalliumvlwinsys += files('vl/vl_winsys_drm.c')
endif

u_indices_gen_c = custom_target(
  'u_indices_gen.c',
  input : 'indices/u_indices_gen.py',
  output : 'u_indices_gen.c',
  command : [prog_python2, '@INPUT@'],
  capture : true,
)

u_unfilled_gen_c = custom_target(
  'u_unfilled_gen.c',
  input : 'indices/u_unfilled_gen.py',
  output : 'u_unfilled_gen.c',
  command : [prog_python2, '@INPUT@'],
  capture : true,
)

u_format_table_c = custom_target(
  'u_format_table.c',
  input : ['util/u_format_table.py', 'util/u_format.csv'],
  output : 'u_format_table.c',
  command : [prog_python2, '@INPUT@'],
  depend_files : files('util/u_format_pack.py', 'util/u_format_parse.py'),
  capture : true,
)

libgallium = static_library(
  'gallium',
  [files_libgallium, u_indices_gen_c, u_unfilled_gen_c, u_format_table_c],
  include_directories : [
    inc_loader, inc_gallium, inc_src, inc_include, include_directories('util')
  ],
  c_args : [c_vis_args, c_msvc_compat_args],
  cpp_args : [cpp_vis_args, cpp_msvc_compat_args],
  dependencies : [
    dep_libdrm, dep_llvm, dep_unwind, dep_dl, dep_m, dep_thread, dep_lmsensors,
    idep_nir_headers,
  ],
  build_by_default : false,
)

libgalliumvl_stub = static_library(
  'galliumvl_stub',
  'vl/vl_stubs.c',
  c_args : [c_vis_args, c_msvc_compat_args],
  cpp_args : [cpp_vis_args, cpp_msvc_compat_args],
  include_directories: [inc_gallium, inc_include, inc_src],
  build_by_default : false,
)

libgalliumvl = static_library(
  'galliumvl',
  files_libgalliumvl,
  c_args : [c_vis_args, c_msvc_compat_args],
  cpp_args : [cpp_vis_args, cpp_msvc_compat_args],
  include_directories : [inc_gallium, inc_include, inc_src],
  build_by_default : false,
)

# XXX: The dependencies here may be off...
libgalliumvlwinsys = static_library(
  'galliumvlwinsys',
  files_libgalliumvlwinsys,
  include_directories : [inc_gallium, inc_include, inc_loader, inc_src],
  dependencies : [dep_libdrm, vlwinsys_deps],
  build_by_default : false,
)
