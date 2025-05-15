# MCP Dart Codegen

A collection of packages that turn **Model Context Protocol (MCP)** annotations into fully-functional Dart servers and tool descriptors.

This repository is a *mono-repo* that hosts:

| Package | Description |
| ------- | ----------- |
| [`packages/mcp_annotations`](packages/mcp_annotations/) | Compile-time annotations (e.g. `@MCPTool`, `@MCPServerApp`) used to describe MCP servers and tools. |
| [`packages/mcp_codegen`](packages/mcp_codegen/) | A [`build_runner`](https://pub.dev/packages/build_runner) generator that converts the annotations above into:  

An **example server** that demonstrates these packages in action can be found under [`examples/demo_server`](examples/demo_server/).

---

## Quick start

Add both packages to your own project:

```yaml
# pubspec.yaml
name: my_app

dependencies:
  mcp_annotations: ^0.1.0

dev_dependencies:
  build_runner: ^2.4.0
  mcp_codegen: ^0.1.0
```

Annotate your functions / classes and run the generator:

```shell
# One-shot build
$ dart run build_runner build

# Or keep it running during development
$ dart run build_runner watch
```

Generated `.mcp.g.dart` files will contain the server entry-points, handler glue code, and JSON descriptors expected by MCP tooling.

---

## Repository layout

```
├── examples/             # Example projects that consume the packages
│   └── demo_server/
├── packages/             # Published Dart packages
│   ├── mcp_annotations/
│   └── mcp_codegen/
├── .github/
└── ...
```

---

## Development

1. Clone the repo and get dependencies:

   ```shell
   $ git clone git@github.com:nelsoncampos-cloudwalk/mcp_dart_codegen.git
   $ cd mcp_dart_codegen
   $ dart pub get
   ```

2. Format & analyse:

   ```shell
   $ dart format .
   $ dart analyze
   ```

3. Run tests:

   ```shell
   $ dart test ./packages/...  # or run from individual package folders
   ```

4. Make your changes following the [contribution guidelines](CONTRIBUTING.md) and open a pull-request.

---

## Contributing

We ❤️ pull-requests!  Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our coding standards, commit conventions, and release process.

---

## License

This project is licensed under the terms of the [Apache 2.0 License](LICENSE). 
