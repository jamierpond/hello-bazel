workspace(name = "hello_world")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# skylib rules
http_archive(
    name = "bazel_skylib",
    sha256 = "bc283cdfcd526a52c3201279cda4bc298652efa898b10b4db0837dc51652756f",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.7.1/bazel-skylib-1.7.1.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.7.1/bazel-skylib-1.7.1.tar.gz",
    ],
)

# Python rules
http_archive(
    name = "rules_python",
    strip_prefix = "rules_python-0.26.0",
    url = "https://github.com/bazelbuild/rules_python/releases/download/0.26.0/rules_python-0.26.0.tar.gz",
)

load("@rules_python//python:pip.bzl", "pip_parse")

# Create a central repo that knows about the dependencies needed to build
# the requirements.txt files.
pip_parse(
    name = "pip",
    requirements_lock = "//python_backend:requirements.txt",
)

load("@pip//:requirements.bzl", "install_deps")
install_deps()


