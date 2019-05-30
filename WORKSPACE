load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "debian_repository_rules",
    branch = "master",
    remote = "https://github.com/fabrand/debian_repository_rules",
)

load("@debian_repository_rules//:debian.bzl", "debian_archive")

debian_archive(
    name = "python3",
    build_file_content = """py_runtime(
    name = "runtime",
    files = glob(["usr/lib/**/*"]),
    interpreter = "usr/bin/python3.7",
    python_version = "PY3",
    visibility = ["//visibility:public"],
)""",
    urls = {
        "http://launchpadlibrarian.net/394585029/python3.7-minimal_3.7.1-1~18.04_amd64.deb": "",
        "http://launchpadlibrarian.net/394585020/libpython3.7-minimal_3.7.1-1~18.04_amd64.deb": "",
        "http://launchpadlibrarian.net/341324234/libpython3.7-stdlib_3.7.0~a2-1_amd64.deb": "",
    },
)

debian_archive(
    name = "python2",
    build_file_content = """py_runtime(
    name = "runtime",
    files = glob(["usr/lib/**/*"]),
    interpreter = "usr/bin/python2.7",
    python_version = "PY2",
    visibility = ["//visibility:public"],
)""",
    urls = {
        "http://launchpadlibrarian.net/365645427/python2.7-minimal_2.7.15~rc1-1_amd64.deb": "",
        "http://launchpadlibrarian.net/412143380/libpython2.7-minimal_2.7.15-4ubuntu4~18.04_amd64.deb": "",
    },
)

register_toolchains("//:python_toolchain")
