load("@bazel_tools//tools/python:toolchain.bzl", "py_runtime_pair")

py_binary(
    name = "dummy_py2",
    srcs = ["dummy_test.py"],
    main = "dummy_test.py",
    python_version = "PY2",
)

py_binary(
    name = "dummy_py3",
    srcs = ["dummy_test.py"],
    main = "dummy_test.py",
    python_version = "PY3",
)

py_runtime_pair(
    name = "py_runtime_pair",
    py2_runtime = "@python2//:runtime",
    py3_runtime = "@python3//:runtime",
    visibility = ["//visibility:public"],
)

toolchain(
    name = "python_toolchain",
    toolchain = ":py_runtime_pair",
    toolchain_type = "@bazel_tools//tools/python:toolchain_type",
    visibility = ["//visibility:public"],
)
