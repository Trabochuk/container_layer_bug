```
➜  container_layer_bug git:(main) ✗ bazel build //...
ERROR: file 'layer-layer.tar.gz' is generated by these conflicting actions:
Label: //:a/layer, //:b/layer
RuleClass: container_layer_ rule
Configuration: 8c7c8a83495a6b29f5e61b94373e857884c6b6f4ed04fcd868a9a81a5d062e34
Mnemonic: GZIP
Action key: 6d2470137bb4f014bdfeb8db4946b6f948ea5d7fdbf7cd6b5ed2ab1687e05085, 0185c4e2af137ccf2e397e81687a91a8961c4ad3a4e7c53008f40357e111b860
Progress message: GZIP layer-layer.tar.gz
PrimaryInput: File:[[<execution_root>]bazel-out/darwin_arm64-fastbuild/bin]a/layer-layer.tar, File:[[<execution_root>]bazel-out/darwin_arm64-fastbuild/bin]b/layer-layer.tar
PrimaryOutput: File:[[<execution_root>]bazel-out/darwin_arm64-fastbuild/bin]layer-layer.tar.gz
ERROR: file 'layer-layer.tar.sha256' is generated by these conflicting actions:
Label: //:a/layer, //:b/layer
RuleClass: container_layer_ rule
Configuration: 8c7c8a83495a6b29f5e61b94373e857884c6b6f4ed04fcd868a9a81a5d062e34
Mnemonic: SHA256
Action key: 7c4e9a1153c54d2c5c74b26c81f3b44629389d4dec3e2a6f40aee2143236afbf, 34daeb28159061a20d99c4bbe131fb8afc078d3f962e51f2ea32de2dd2a3a290
Progress message: SHA256 layer-layer.tar.sha256
PrimaryInput: File:[[<execution_root>]bazel-out/darwin_arm64-fastbuild/bin]a/layer-layer.tar, File:[[<execution_root>]bazel-out/darwin_arm64-fastbuild/bin]b/layer-layer.tar
PrimaryOutput: File:[[<execution_root>]bazel-out/darwin_arm64-fastbuild/bin]layer-layer.tar.sha256
ERROR: com.google.devtools.build.lib.skyframe.ArtifactConflictFinder$ConflictException: com.google.devtools.build.lib.actions.MutableActionGraph$ActionConflictException: for layer-layer.tar.sha256, previous action: action 'SHA256 layer-layer.tar.sha256', attempted action: action 'SHA256 layer-layer.tar.sha256'
INFO: Elapsed time: 0.155s
INFO: 0 processes.
FAILED: Build did NOT complete successfully (24 packages loaded, 181 targets configured)
```
