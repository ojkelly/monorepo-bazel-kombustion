workspace(name = "bazel_kombustion_monorepo_example")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

# Create a Label for the Kombustion rules repo
git_repository(
    name = "io_bazel_rules_kombustion",
    commit = "ab368b8c53f6f699bd9a3a15d85752d83180ee05",
    remote = "https://github.com/KablamoOSS/rules_kombustion.git",
)
