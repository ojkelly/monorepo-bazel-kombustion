load("@io_bazel_rules_kombustion//:kombustion.bzl", "kombustion")
load("@io_bazel_rules_kombustion//:lambda.bzl", "lambda_upload")

kombustion(
    name = "deploy",
    kombustion = "//src/mars/pipeline:kombustion",
    stacks = ["StepOneStack.yaml"],
)

lambda_upload(
    name = "lambda",
    # Folders to be zipped up for our lambda
    # The leading paths are stripped `zip -j`
    src = [
        "src",
    ],
    # The bucket to store this lambda in
    # the key is automatically derived from the path to this target,
    # in this case the final zip could be found at:
    # s3://lambda.infrastructure.jupiter.example/srv/mars/pipeline/stepOne/lambda.zip
    bucket = "lambda.infrastructure.jupiter.example",
)
