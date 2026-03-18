# README.md

Circuits data files:
1. circuitsv2.json - The Circuits V2 chips normally shown in the pallette.
2. circuitsv2.full.json - The Circuits V2 chips shown in the palette plus additional chips which are hidden or dev-only.
3. descriptor_set.binpb - The protobuf descriptor set.

## descriptor_set.binpb

You can read this file as proto descriptors with `protoc` or `bun`.

With [`protoc`](https://protobuf.dev/installation/):

```sh
protoc --decode=google.protobuf.FileDescriptorSet google/protobuf/descriptor.proto < descriptor_set.binpb
```

With [`buf`](https://github.com/bufbuild/buf):

```sh
buf convert --type google.protobuf.FileDescriptorSet --from descriptor_set.binpb --to -#format=txtpb

```

Note that these are only descriptions of the .proto files. They are not the original .proto files used in game.
