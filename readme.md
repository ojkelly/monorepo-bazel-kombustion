# Kombustion Bazel Monorepo

[rules_kombustion](https://github.com/KablamoOSS/rules_kombustion)
[Kombustion](https://github.com/KablamoOSS/kombustion)
[Getting Started with Bazel](https://docs.bazel.build/versions/master/getting-started.html)

## Getting Started

To deploy the lambda bucket run:

```
bazel run //src/jupiter/infrastructure:deploy -- --profile={awsProfileHere}
```

Then upload the lambda:

```
bazel run //src/mars/pipeline/stepOne:lambda -- --profile={awsProfileHere}
```

To deploy the lambda for stepOne run:

```
bazel run //src/mars/pipeline/stepOne:deploy -- --profile={awsProfileHere}
```

## Layout

Because Bazel build targets are defined by a `BUILD` file, the folder structure
you choose is, for the most part, completely arbitrary.

With that in mind, this example presents a structure with 2 main levels. The top
being a Realm, and the folders below, being domains.

```
.
├── WORKSPACE
├── readme.md
└── src                                     # Source Code
    ├── jupiter                             # Realm: jupiter
    │   └── infrastructure                  # Domain: infrastructure
    │       ├── BUILD                       # Infrastructure build file
    │       ├── LambdaStorageStack.yaml     # Lambda S3 Bucket stack
    │       └── kombustion.yaml             # Kombustion manifest file
    └── mars                                # Realm: mars
        └── pipeline                        # Domain: pipeline
            ├── BUILD                       # BUILD file to create a target for kombustion.yaml
            ├── kombustion.yaml             # manifest file for mars/pipeline
            ├── stepOne                     # lambda
            │   ├── BUILD                   # lambda build file
            │   ├── StepOneStack.yaml       # lambda CloudFormation stack
            │   └── src                     # lambda source
            │       └── lambda.py
            ├── stepThree
            │   ├── BUILD
            │   ├── StepThreeStack.yaml
            │   └── src
            │       └── lambda.py
            └── stepTwo
                ├── BUILD
                ├── StepTwoStack.yaml
                └── src
```
