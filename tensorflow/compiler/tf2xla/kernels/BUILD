licenses(["notice"])  # Apache 2.0

package(
    default_visibility = ["//tensorflow/compiler/tf2xla:internal"],
)

load("//tensorflow:tensorflow.bzl", "tf_copts")
load("//tensorflow:tensorflow.bzl", "tf_kernel_library")
load(
    "//third_party/mkl:build_defs.bzl",
    "if_mkl",
)

tf_kernel_library(
    name = "xla_ops",
    srcs = [
        "aggregate_ops.cc",
        "arg_op.cc",
        "batch_matmul_op.cc",
        "batch_norm_op.cc",
        "batchtospace_op.cc",
        "bcast_ops.cc",
        "bias_ops.cc",
        "binary_ops.cc",
        "broadcast_to_op.cc",
        "bucketize_op.cc",
        "cast_op.cc",
        "categorical_op.cc",
        "cholesky_op.cc",
        "clip_by_value_op.cc",
        "concat_op.cc",
        "const_op.cc",
        "conv_ops.cc",
        "cross_op.cc",
        "cwise_ops.cc",
        "cwise_ops.h",
        "depthtospace_op.cc",
        "diag_op.cc",
        "dynamic_slice_ops.cc",
        "dynamic_stitch_op.cc",
        "elu_op.cc",
        "extract_image_patches_op.cc",
        "fake_quantize_ops.cc",
        "fft_ops.cc",
        "fill_op.cc",
        "function_ops.cc",
        "gather_op.cc",
        "gather_op_helpers.h",
        "identity_op.cc",
        "image_ops.cc",
        "image_resize_ops.cc",
        "index_ops.cc",
        "l2loss_op.cc",
        "listdiff_op.cc",
        "lrn_ops.cc",
        "matmul_op.cc",
        "matrix_band_part_op.cc",
        "matrix_set_diag_op.cc",
        "matrix_triangular_solve_op.cc",
        "mirror_pad_op.cc",
        "no_op.cc",
        "one_hot_op.cc",
        "pack_op.cc",
        "pad_op.cc",
        "permute_op.cc",
        "pooling_ops.cc",
        "qr_op.cc",
        "quantize_and_dequantize_op.cc",
        "random_ops.cc",
        "reduce_window_op.cc",
        "reduction_ops.cc",
        "reduction_ops.h",
        "reduction_ops_common.cc",
        "relu_op.cc",
        "reshape_op.cc",
        "retval_op.cc",
        "reverse_op.cc",
        "reverse_sequence_op.cc",
        "scan_ops.cc",
        "scatter_nd_op.cc",
        "segment_reduction_ops.cc",
        "select_op.cc",
        "sendrecv_ops.cc",
        "sequence_ops.cc",
        "shape_op.cc",
        "shape_util.cc",
        "slice_op.cc",
        "softmax_op.cc",
        "sort_ops.cc",
        "spacetobatch_op.cc",
        "spacetodepth_op.cc",
        "sparse_to_dense_op.cc",
        "split_op.cc",
        "stack_ops.cc",
        "stateless_random_ops.cc",
        "strided_slice_op.cc",
        "tensor_array_ops.cc",
        "tensor_list_ops.cc",
        "tile_ops.cc",
        "topk_op.cc",
        "training_ops.cc",
        "transpose_op.cc",
        "unary_ops.cc",
        "unpack_op.cc",
        "variable_ops.cc",
        "xla_broadcast_helper_op.cc",
        "xla_conv_op.cc",
        "xla_dot_op.cc",
        "xla_pad_op.cc",
        "xla_reduce_op.cc",
        "xla_select_and_scatter_op.cc",
    ],
    hdrs = [
        "index_ops.h",
        "shape_util.h",
    ],
    deps = [
        ":conv_op_helpers",
        ":if_op",
        ":while_op",
        "//tensorflow/compiler/tf2xla:common",
        "//tensorflow/compiler/tf2xla:xla_compiler",
        "//tensorflow/compiler/tf2xla/lib:batch_dot",
        "//tensorflow/compiler/tf2xla/lib:broadcast",
        "//tensorflow/compiler/tf2xla/lib:cholesky",
        "//tensorflow/compiler/tf2xla/lib:qr",
        "//tensorflow/compiler/tf2xla/lib:random",
        "//tensorflow/compiler/tf2xla/lib:scatter",
        "//tensorflow/compiler/tf2xla/lib:triangular_solve",
        "//tensorflow/compiler/tf2xla/lib:util",
        "//tensorflow/compiler/tf2xla/lib:while_loop",
        "//tensorflow/compiler/tf2xla/ops:xla_ops",
        "//tensorflow/compiler/xla:array4d",
        "//tensorflow/compiler/xla:literal",
        "//tensorflow/compiler/xla:literal_util",
        "//tensorflow/compiler/xla:shape_util",
        "//tensorflow/compiler/xla:status_macros",
        "//tensorflow/compiler/xla:util",
        "//tensorflow/compiler/xla:xla_data_proto",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:xla_builder",
        "//tensorflow/compiler/xla/client:xla_computation",
        "//tensorflow/compiler/xla/client/lib:arithmetic",
        "//tensorflow/compiler/xla/client/lib:constants",
        "//tensorflow/compiler/xla/client/lib:math",
        "//tensorflow/compiler/xla/client/lib:numeric",
        "//tensorflow/compiler/xla/client/lib:pooling",
        "//tensorflow/compiler/xla/client/lib:prng",
        "//tensorflow/compiler/xla/client/lib:sorting",
        "//tensorflow/core:framework",
        "//tensorflow/core:image_ops_op_lib",
        "//tensorflow/core:lib",
        "//tensorflow/core:linalg_ops_op_lib",
        "//tensorflow/core:protos_all_cc",
        "//tensorflow/core:spectral_ops_op_lib",
        "//tensorflow/core:stateless_random_ops_op_lib",
        "//tensorflow/core/kernels:bounds_check",
        "//tensorflow/core/kernels:concat_lib",
        "//tensorflow/core/kernels:constant_op",
        "//tensorflow/core/kernels:control_flow_ops",
        "//tensorflow/core/kernels:conv_ops",
        "//tensorflow/core/kernels:cwise_op",
        "//tensorflow/core/kernels:list_kernels",
        "//tensorflow/core/kernels:no_op",
        "//tensorflow/core/kernels:ops_util",
        "//tensorflow/core/kernels:pooling_ops",
        "//tensorflow/core/kernels:random_op",
        "//tensorflow/core/kernels:resource_variable_ops",
        "//tensorflow/core/kernels:sendrecv_ops",
        "//tensorflow/core/kernels:sparse_to_dense_op",
        "//tensorflow/core/kernels:stack_ops",
        "//tensorflow/core/kernels:training_ops",
        "//tensorflow/core/kernels:transpose_op",
        "@com_google_absl//absl/algorithm:container",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/types:span",
    ],
)

cc_library(
    name = "conv_op_helpers",
    srcs = ["conv_op_helpers.cc"],
    hdrs = ["conv_op_helpers.h"],
    deps = [
        "//tensorflow/compiler/tf2xla:common",
        "//tensorflow/compiler/tf2xla:xla_compiler",
        "//tensorflow/compiler/xla:literal_util",
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla/client:xla_builder",
        "//tensorflow/compiler/xla/client/lib:arithmetic",
        "//tensorflow/compiler/xla/client/lib:constants",
        "//tensorflow/compiler/xla/client/lib:numeric",
        "//tensorflow/core:framework",
        "//tensorflow/core/kernels:bounds_check",
        "//tensorflow/core/kernels:conv_ops",
        "//tensorflow/core/kernels:ops_util",
        "@com_google_absl//absl/types:span",
    ],
)

tf_kernel_library(
    name = "while_op",
    srcs = ["while_op.cc"],
    hdrs = ["while_op.h"],
    deps = [
        "//tensorflow/compiler/tf2xla:common",
        "//tensorflow/compiler/tf2xla:side_effect_util",
        "//tensorflow/compiler/tf2xla:xla_compiler",
        "//tensorflow/compiler/tf2xla/ops:xla_ops",
        "//tensorflow/compiler/xla:literal",
        "//tensorflow/compiler/xla/client:xla_builder",
        "//tensorflow/compiler/xla/client:xla_computation",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core:protos_all_cc",
    ],
)

tf_kernel_library(
    name = "if_op",
    srcs = ["if_op.cc"],
    hdrs = ["if_op.h"],
    deps = [
        "//tensorflow/compiler/tf2xla:common",
        "//tensorflow/compiler/tf2xla:side_effect_util",
        "//tensorflow/compiler/tf2xla:xla_compiler",
        "//tensorflow/compiler/tf2xla/ops:xla_ops",
        "//tensorflow/compiler/xla:literal",
        "//tensorflow/compiler/xla/client:xla_builder",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core:protos_all_cc",
    ],
)

# Kernels that have a dummy (no-op) implementation.
tf_kernel_library(
    name = "xla_dummy_ops",
    srcs = [
        "assert_op.cc",
        "check_numerics_op.cc",
    ],
    deps = [
        "//tensorflow/compiler/tf2xla:xla_compiler",
        "//tensorflow/core:array_ops_op_lib",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core:logging_ops_op_lib",
    ],
    alwayslink = 1,
)

# Kernels that only work on CPU, because they use XLA custom calls.
# Only link this when using the CPU backend for XLA.
tf_kernel_library(
    name = "xla_cpu_only_ops",
    srcs = ["index_ops_cpu.cc"],
    deps = [
        ":index_ops_kernel_argmax_float_1d",
        ":index_ops_kernel_argmax_float_2d",
        "//tensorflow/compiler/tf2xla:common",
        "//tensorflow/compiler/tf2xla:xla_compiler",
        "//tensorflow/compiler/xla:literal",
        "//tensorflow/compiler/xla:literal_util",
        "//tensorflow/compiler/xla/client:client_library",
        "//tensorflow/compiler/xla/client:xla_builder",
        "//tensorflow/compiler/xla/client/lib:arithmetic",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core/kernels:argmax_op",
        "//tensorflow/core/kernels:bounds_check",
    ],
)

cc_library(
    name = "index_ops_kernel_argmax_float_1d",
    srcs = ["index_ops_kernel_argmax_float_1d.cc"],
    copts = tf_copts(),
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow/compiler/xla/service/cpu:custom_call_target_registry",
        "//tensorflow/core:framework_lite",
        "//third_party/eigen3",
    ],
    alwayslink = 1,
)

cc_library(
    name = "index_ops_kernel_argmax_float_2d",
    srcs = ["index_ops_kernel_argmax_float_2d.cc"],
    copts = tf_copts(),
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow/compiler/xla/service/cpu:custom_call_target_registry",
        "//tensorflow/core:framework_lite",
        "//third_party/eigen3",
    ],
    alwayslink = 1,
)
