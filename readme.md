# Kombustion Bazel Monorepo

To deploy the lambda bucket run:

```
bazel run //src/jupiter/infrastructure:deploy -- --profile={awsProfileHere} --environment=Development
```

Then upload the lambda:

```
bazel run //src/mars/pipeline/stepOne:lambda -- --profile={awsProfileHere} --environment=Development
```

To deploy the lambda for stepOne run:

```
bazel run //src/mars/pipeline/stepOne:deploy -- --profile={awsProfileHere} --environment=Development --iam
```
