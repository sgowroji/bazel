load("@rules_python//python:py_binary.bzl", "py_binary")
load("@rules_python//python:py_library.bzl", "py_library")
load("@rules_python//python:py_test.bzl", "py_test")

filegroup(
    name = "srcs",
    srcs = glob(["*.py"]) + [
        "BUILD",
        "//examples/py_native/fibonacci:srcs",
    ],
    visibility = ["//examples:__pkg__"],
)

py_binary(
    name = "bin",
    srcs = ["bin.py"],
    deps = [
        ":lib",
        "//examples/py_native/fibonacci",
    ],
)

py_library(
    name = "lib",
    srcs = ["lib.py"],
)

py_test(
    name = "test",
    srcs = ["test.py"],
    deps = [
        ":lib",
        "//examples/py_native/fibonacci",
    ],
)

py_test(
    name = "fail",
    srcs = ["fail.py"],
    deps = [":lib"],
)
