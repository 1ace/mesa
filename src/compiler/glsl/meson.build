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

subdir('glcpp')

glsl_parser = custom_target(
  'glsl_parser',
  input : 'glsl_parser.yy',
  output : ['glsl_parser.cpp', 'glsl_parser.h'],
  command : [
    prog_bison, '-o', '@OUTPUT0@', '-p', '_mesa_glsl_', '--defines=@OUTPUT1@',
    '@INPUT@',
  ],
)

glsl_lexer_cpp = custom_target(
  'glsl_lexer_cpp',
  input : 'glsl_lexer.ll',
  output : 'glsl_lexer.cpp',
  command : [prog_flex, '-o', '@OUTPUT@', '@INPUT@'],
)

ir_expression_operation_constant_h = custom_target(
  'ir_expression_operation_constant.h',
  input : 'ir_expression_operation.py',
  output : 'ir_expression_operation_constant.h',
  command : [prog_python2, '@INPUT@', 'constant'],
  capture : true,
)

ir_expression_operation_strings_h = custom_target(
  'ir_expression_operation_strings.h',
  input : 'ir_expression_operation.py',
  output : 'ir_expression_operation_strings.h',
  command : [prog_python2, '@INPUT@', 'strings'],
  capture : true,
)

files_libglsl = files(
  'ast_array_index.cpp',
  'ast_expr.cpp',
  'ast_function.cpp',
  'ast_to_hir.cpp',
  'ast_type.cpp',
  'builtin_functions.cpp',
  'builtin_types.cpp',
  'builtin_variables.cpp',
  'generate_ir.cpp',
  'gl_nir_lower_atomics.c',
  'gl_nir_lower_samplers.c',
  'gl_nir_lower_samplers_as_deref.c',
  'glsl_parser_extras.cpp',
  'glsl_symbol_table.cpp',
  'glsl_to_nir.cpp',
  'hir_field_selection.cpp',
  'ir_array_refcount.cpp',
  'ir_basic_block.cpp',
  'ir_builder.cpp',
  'ir_clone.cpp',
  'ir_constant_expression.cpp',
  'ir.cpp',
  'ir_equals.cpp',
  'ir_expression_flattening.cpp',
  'ir_function_can_inline.cpp',
  'ir_function_detect_recursion.cpp',
  'ir_function.cpp',
  'ir_hierarchical_visitor.cpp',
  'ir_hv_accept.cpp',
  'ir_print_visitor.cpp',
  'ir_reader.cpp',
  'ir_rvalue_visitor.cpp',
  'ir_set_program_inouts.cpp',
  'ir_validate.cpp',
  'ir_variable_refcount.cpp',
  'linker.cpp',
  'link_atomics.cpp',
  'link_functions.cpp',
  'link_interface_blocks.cpp',
  'link_uniforms.cpp',
  'link_uniform_initializers.cpp',
  'link_uniform_block_active_visitor.cpp',
  'link_uniform_blocks.cpp',
  'link_varyings.cpp',
  'loop_analysis.cpp',
  'loop_unroll.cpp',
  'lower_blend_equation_advanced.cpp',
  'lower_buffer_access.cpp',
  'lower_const_arrays_to_uniforms.cpp',
  'lower_cs_derived.cpp',
  'lower_discard.cpp',
  'lower_discard_flow.cpp',
  'lower_distance.cpp',
  'lower_if_to_cond_assign.cpp',
  'lower_instructions.cpp',
  'lower_int64.cpp',
  'lower_jumps.cpp',
  'lower_mat_op_to_vec.cpp',
  'lower_noise.cpp',
  'lower_offset_array.cpp',
  'lower_packed_varyings.cpp',
  'lower_named_interface_blocks.cpp',
  'lower_packing_builtins.cpp',
  'lower_subroutine.cpp',
  'lower_tess_level.cpp',
  'lower_texture_projection.cpp',
  'lower_variable_index_to_cond_assign.cpp',
  'lower_vec_index_to_cond_assign.cpp',
  'lower_vec_index_to_swizzle.cpp',
  'lower_vector.cpp',
  'lower_vector_derefs.cpp',
  'lower_vector_insert.cpp',
  'lower_vertex_id.cpp',
  'lower_output_reads.cpp',
  'lower_shared_reference.cpp',
  'lower_ubo_reference.cpp',
  'opt_algebraic.cpp',
  'opt_array_splitting.cpp',
  'opt_conditional_discard.cpp',
  'opt_constant_folding.cpp',
  'opt_constant_propagation.cpp',
  'opt_constant_variable.cpp',
  'opt_copy_propagation.cpp',
  'opt_copy_propagation_elements.cpp',
  'opt_dead_builtin_variables.cpp',
  'opt_dead_builtin_varyings.cpp',
  'opt_dead_code.cpp',
  'opt_dead_code_local.cpp',
  'opt_dead_functions.cpp',
  'opt_flatten_nested_if_blocks.cpp',
  'opt_flip_matrices.cpp',
  'opt_function_inlining.cpp',
  'opt_if_simplification.cpp',
  'opt_minmax.cpp',
  'opt_rebalance_tree.cpp',
  'opt_redundant_jumps.cpp',
  'opt_structure_splitting.cpp',
  'opt_swizzle.cpp',
  'opt_tree_grafting.cpp',
  'opt_vectorize.cpp',
  'propagate_invariance.cpp',
  's_expression.cpp',
  'string_to_uint_map.cpp',
  'serialize.cpp',
  'shader_cache.cpp',
)

files_libglsl_standalone = files(
  'ir_builder_print_visitor.cpp',
  'standalone_scaffolding.cpp',
  'standalone.cpp',
)

libglsl = static_library(
  'glsl',
  [files_libglsl, glsl_parser, glsl_lexer_cpp, ir_expression_operation_h,
   ir_expression_operation_strings_h, ir_expression_operation_constant_h],
  c_args : [c_vis_args, c_msvc_compat_args, no_override_init_args],
  cpp_args : [cpp_vis_args, cpp_msvc_compat_args],
  link_with : libglcpp,
  include_directories : [inc_common, inc_compiler, inc_nir],
  dependencies : idep_nir,
  build_by_default : false,
)

libglsl_standalone = static_library(
  'glsl_standalone',
  [files_libglsl_standalone, ir_expression_operation_h],
  c_args : [c_vis_args, c_msvc_compat_args, no_override_init_args],
  cpp_args : [cpp_vis_args, cpp_msvc_compat_args],
  include_directories : [inc_common],
  link_with : [libglsl, libglsl_util, libmesa_util],
  dependencies : [dep_thread],
  build_by_default : false,
)

glsl_compiler = executable(
  'glsl_compiler',
  'main.cpp',
  c_args : [c_vis_args, c_msvc_compat_args, no_override_init_args],
  cpp_args : [cpp_vis_args, cpp_msvc_compat_args],
  dependencies : [dep_clock, dep_thread],
  include_directories : [inc_common],
  link_with : [libglsl_standalone],
  build_by_default : with_tools.contains('glsl'),
  install : with_tools.contains('glsl'),
)

glsl_test = executable(
  'glsl_test',
  [files('test.cpp', 'test_optpass.cpp'), ir_expression_operation_h],
  c_args : [c_vis_args, c_msvc_compat_args, no_override_init_args],
  cpp_args : [cpp_vis_args, cpp_msvc_compat_args],
  include_directories : [inc_common],
  dependencies : [dep_clock, dep_thread],
  link_with : [libglsl, libglsl_standalone, libglsl_util],
  build_by_default : with_tools.contains('glsl'),
  install : with_tools.contains('glsl'),
)

if with_tests
  subdir('tests')
endif
