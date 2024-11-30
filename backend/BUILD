load("@rules_python//python:defs.bzl", "py_binary")
load("@pip//:requirements.bzl", "requirement")

py_binary(
    name = "backend",
    srcs = ["src/main.py"],
    deps = [
        requirement("flask"),
    ],
)
