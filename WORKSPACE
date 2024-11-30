workspace(name = "hello_world")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Python rules
http_archive(
    name = "rules_python",
    strip_prefix = "rules_python-0.26.0",
    url = "https://github.com/bazelbuild/rules_python/releases/download/0.26.0/rules_python-0.26.0.tar.gz",
)

# Load Python basic setup
load("@rules_python//python:repositories.bzl", "py_repositories")
py_repositories()

# Load pip setup
load("@rules_python//python:pip.bzl", "pip_parse")

# Create a central repo for pip dependencies
pip_parse(
    name = "pip",
    requirements_lock = "//backend:requirements.txt",
)

# Load pip requirements
load("@pip//:requirements.bzl", "install_deps")
install_deps()
