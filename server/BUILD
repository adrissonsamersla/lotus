load("@crate_index//:defs.bzl", "all_crate_deps")
load("@rules_rust//rust:defs.bzl", "rust_binary")

rust_binary(
    name = "server",
    srcs = ["src/main.rs"],
    edition = "2018",
    deps = all_crate_deps(
        normal = True,
    ),
    proc_macro_deps = all_crate_deps(
        proc_macro = True,
    ),
)
