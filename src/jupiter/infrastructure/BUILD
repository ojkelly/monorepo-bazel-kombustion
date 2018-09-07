package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_kombustion//:kombustion.bzl", "kombustion", "kombustion_library")

# Export the kombustion config
kombustion_library(
    name = "kombustion",
    manifest = "kombustion.yaml",
    # Currently we don't have any plugins, so we've commented out the plugin files
    # lock = "kombustion.lock",
    # plugins = glob([
    #     ".kombustion/**",
    # ]),
)

# Create a deploy target for our Lambda Storage Bucket
kombustion(
    name = "deploy",
    kombustion = "//src/jupiter/infrastructure:kombustion",
    templates = glob(["*Stack.yaml"]),
)
