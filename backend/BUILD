load("@rules_python//python:defs.bzl", "py_binary")
load("@pip//:requirements.bzl", "requirement")

py_binary(
    name = "backend",
    srcs = ["backend.py"],
    deps = [
        requirement("flask"),
        requirement("Werkzeug"),
        requirement("Jinja2"),
        requirement("itsdangerous"),
        requirement("click"),
        requirement("blinker"),
    ],
    visibility = ["//visibility:public"],
)

exports_files(["requirements.txt", "requirements_lock.txt"])
