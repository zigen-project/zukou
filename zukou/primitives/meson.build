frame_cuboid_vertex_glsl = custom_target(
  'primitive-frame-cuboid-vert.h',
  command: cmd_textify + [ '-n', 'primitive_frame_cuboid_vertex_shader' ],
  input: 'frame-cuboid.vert',
  output: 'primitive-frame-cuboid-vert.h'
)

frame_cuboid_fragment_glsl = custom_target(
  'primitive-frame-cuboid-frag.h',
  command: cmd_textify + [ '-n', 'primitive_frame_cuboid_fragment_shader' ],
  input: 'frame-cuboid.frag',
  output: 'primitive-frame-cuboid-frag.h'
)

deps_zukou_primitives = [
  dep_glm,
]

srcs_zukou_primitives = [
  'frame-cuboid.cc',
  frame_cuboid_fragment_glsl,
  frame_cuboid_vertex_glsl,
  zigen_opengl_client_protocol_h,
]

lib_zukou_primitives = static_library(
  'zukou-primitives',
  srcs_zukou_primitives,
  install : false,
  dependencies : deps_zukou_primitives,
  include_directories : public_inc,
)

dep_zukou_primitives = declare_dependency(
  link_with : lib_zukou_primitives,
  include_directories : public_inc,
)
