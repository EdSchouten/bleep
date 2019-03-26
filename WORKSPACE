load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "77dfd303492f2634de7a660445ee2d3de2960cbd52f97d8c0dffa9362d3ddef9",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/0.18.1/rules_go-0.18.1.tar.gz"],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "3c681998538231a2d24d0c07ed5a7658cb72bfb5fd4bf9911157c0e9ac6a2687",
    urls = ["https://github.com/bazelbuild/bazel-gazelle/releases/download/0.17.0/bazel-gazelle-0.17.0.tar.gz"],
)

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "com_github_bazelbuild_bazel_buildfarm",
    commit = "504559a20da843d947d34e40af59b080ebd2a33a",
    patches = ["//:go_package.diff"],
    remote = "https://github.com/bazelbuild/bazel-buildfarm.git",
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")

gazelle_dependencies()

load("@bazel_gazelle//:deps.bzl", "go_repository")

go_repository(
    name = "com_github_bazelbuild_remote_apis",
    importpath = "github.com/bazelbuild/remote-apis",
    sha256 = "99ab1378f10854504c75bcfa43be2129d36bbba8e80a79a4216a3e3026a0985b",
    strip_prefix = "remote-apis-ed4849810292e5fb3c844992133523f01a4ad420",
    urls = ["https://github.com/bazelbuild/remote-apis/archive/ed4849810292e5fb3c844992133523f01a4ad420.tar.gz"],
)
