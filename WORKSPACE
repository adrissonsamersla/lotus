load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

#
# loading
#

# rules rust

http_archive(
    name = "rules_rust",
    sha256 = "aaaa4b9591a5dad8d8907ae2dbe6e0eb49e6314946ce4c7149241648e56a1277",
    urls = ["https://github.com/bazelbuild/rules_rust/releases/download/0.16.1/rules_rust-v0.16.1.tar.gz"],
)

load("@rules_rust//rust:repositories.bzl", "rules_rust_dependencies", "rust_register_toolchains")
rules_rust_dependencies()

#
# registering toolchains
#

rust_register_toolchains(
    edition = "2018",
)

#
# handling rust dependencies
#

load("@rules_rust//crate_universe:defs.bzl", "crates_repository")

crates_repository(
    name = "crate_index",
    cargo_lockfile = "//:Cargo.lock",
    lockfile = "//:Cargo.Bazel.lock",
    manifests = [
        "//:Cargo.toml",
        "//server:Cargo.toml"
    ],
)

load("@crate_index//:defs.bzl", "crate_repositories")

crate_repositories()
