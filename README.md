This is a featuregate linter that can be compiled into a plugin for `golangci-lint`.

### Create the Plugin From This Linter

1. From the root project directory, run `go build -buildmode=plugin plugin/featuregate.go`.
2. This repo has a `.golangci-lint` file so run commands from this directory so that the plugin is available via the config.

### Run this linter
To run this linter with golangci-lint, use the below command from the root directory
```
$ golangci-lint cache clean; golangci-lint run -v  --disable-all --enable=featuregate testdata/*.go
```

To debug via the file that the plugin creates while the PR is still WIP, use the below command from the root directory:
```
rm feature_gate_linter.log; golangci-lint cache clean; golangci-lint run -v  --disable-all --enable=featuregate testdata/*.go; cat feature_gate_linter.log;
```