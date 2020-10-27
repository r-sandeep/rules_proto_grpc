# Changelog

## Unreleased

- Added `copt` argument pass-through for Obj-C library rules.
- Added `CHANGELOG.md`


## 2.0.0

### General
- Updated `protobuf` to 3.13.0
- Updated `grpc` to 1.32.0
- **WORKSPACE update needed**: These rules now depend on `rules_proto`, which must be added to your WORKSPACE file
- Dropped support for the deprecated `transitivity` attribute on `proto_plugin`. The `exclusions` attribute is the supported way of achieving this
- The `output_dirs` attribute of `ProtoCompileInfo` is now a depset, meaning directories will be deduplicated
- Removed the `deps.bzl` files that have been deprecated since version 1.0.0
- Tags are now propagated correctly on library rules

### Android
- **WORKSPACE update needed**: The Guava dependency is no longer needed

### C#
- Updated `rules_dotnet` to latest master
- Updated `Google.Protobuf` to 3.13.0
- Updated `Grpc` to 2.32.0
- **WORKSPACE update needed**: There have been substantial changes to the required WORKSPACE rules for C#. Please see the C# language page

### Closure
- Updated `rules_closure` to 0.11.0

### D
- Updated `rules_d` to latest master
- Updated `protobuf-d` to 0.6.2

### grpc-gateway
- Updated `grpc-gateway` to 1.15.0

### gRPC Web
- Updated gRPC Web to 1.2.1

### Go
- Updated `rules_go` to 0.24.3
- Updated `bazel-gazelle` to 0.21.1
- Updated `org_golang_x_net` to v0.0.0-20200930145003-4acb6c075d10
- Updated `org_golang_x_text` to 0.3.3

### Java
- **WORKSPACE update needed**: The Guava dependency is no longer needed

### NodeJS
- Updated `rules_nodejs` to 2.2.0
- **WORKSPACE update needed**: The `defs.bzl` file in `rules_nodejs` has moved to `index.bzl`
- **WORKSPACE update needed**: Running `yarn_install()` is needed in more cases
- **WORKSPACE update needed**: Running `grpc_deps()` is no longer necessary for just the NodeJS rules
- Moved from `grpc` to `@grpc/grpc-js` package
- Library rules have been enabled and now return `js_library` rather than `npm_package`

### Python
- Dropped Python 2 support
- Updated `rules_python` to latest master
- Updated `grpclib` to 0.4.1
- Moved to using `grpcio` library directly from the local `grpc` repository.
- Pinned dependency versions in requirements.txt using pip-compile
- **WORKSPACE update needed**: The method for loading Pip dependencies has changed. Please see the Python language page.
- **WORKSPACE update needed**: Using the Pip dependencies is now only necessary if you are using the `grpclib` rules

### Rust:
- Updated `rules_rust` to latest master
- Updated `protobuf` crate to 2.17.0
- Updated `grpcio` crate to 0.6.0
- **WORKSPACE update needed**: The setup for `rules_rust` has changed in the newer version. Please see the Rust language page.
- **WORKSPACE update needed**: The `grpc_deps()` rule is now needed for Rust

### Scala:
- Updated `rules_scala` to latest master
- `ScalaPB` is now pulled from `rules_scala`, which uses 0.9.7
- **WORKSPACE update needed**: The `scala_proto_repositories()` rule is now needed

### Swift:
- Updated `rules_swift` to 0.15.0
- Updated `grpc-swift` to 0.11.0
- Moved the Swift library rules to be internal to this repo


## 1.0.2

### Android / Closure / Java / Scala

- Fixed loading of `com_google_errorprone_error_prone_annotations`
- Replaced Maven HTTP URLs with HTTPS URLs
- Updated grpc-java, rules_closure and rules_scala to include Maven HTTPS fix


## 1.0.1

### General

- Fix support for plugins that use `output_directory` and produce no output files: #39 
- Misc typo fixes and tidying


## 1.0.0

### General

- Bazel 1.0+ is now supported
- The `rules_proto_grpc_repos()` WORKSPACE rule has been added and is recommended to be used
- Protobuf has been updated to 3.11.0
- gRPC has been updated to 1.25.0
- All other dependencies have been updated where available
- The Bazel version is now checked for compatibility
- Added more test workspaces
- Removed tests that use `proto_source_root`
- Added fix for duplicate proto files when using `import_prefix`

### Closure

- The required WORKSPACE rules has been updated for all Closure-based rules, please check the documentation for the current recommended set

### Go / GoGo / grpc-gateway

- The required WORKSPACE rules has been updated for all Go-based rules, please check the documentation for the current recommended set

### gRPC.js

- Support for gRPC.js has been removed

### Python

- The way dependencies are pulled in has changed from using `rules_pip` to the standard `rules_python`. Please check the documentation for the new WORKSPACE rules required and remove the old ones

### Scala

- Scala gRPC rules are currently not working fully. Due to delays in publishing support for Bazel 1.0, this support has been pushed back to 1.1.0
- The required WORKSPACE rules has been updated for all Scala rules, please check the documentation for the current recommended set


## 0.2.0

### General
- Tests generated by the routeguide test matrix now correctly us the client/server executables

### Ruby
- Well-known proto files are excluded from generation in the Ruby plugins
- The naming of the Ruby gems workspace has changed to remove the 'routeguide' prefix
- Ruby client/server is now included in the non-manual test matrix


# 0.1.0

Initial release of `rules_proto_grpc`. For changes from predecessor `rules_proto`, please see [MIGRATION.md](https://github.com/rules-proto-grpc/rules_proto_grpc/blob/master/docs/MIGRATION.md)