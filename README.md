# Swift OpenAPI Generator Runtime

[![](https://img.shields.io/badge/docc-read_documentation-blue)](https://swiftpackageindex.com/apple/swift-openapi-runtime/documentation)
[![](https://img.shields.io/endpoint?url=https%3A%2F%2Fswiftpackageindex.com%2Fapi%2Fpackages%2Fapple%2Fswift-openapi-runtime%2Fbadge%3Ftype%3Dswift-versions)](https://swiftpackageindex.com/apple/swift-openapi-runtime)
[![](https://img.shields.io/endpoint?url=https%3A%2F%2Fswiftpackageindex.com%2Fapi%2Fpackages%2Fapple%2Fswift-openapi-runtime%2Fbadge%3Ftype%3Dplatforms)](https://swiftpackageindex.com/apple/swift-openapi-runtime)

This library provides common abstractions and helper functions used by the client and server code generated by [Swift OpenAPI Generator][0].

## Overview

It contains:
- Common types used in the code generated by the `swift-openapi-generator` package plugin.
- Protocol definitions for pluggable layers, including `ClientTransport`, `ServerTransport`, and middleware.

## Usage

Add the package dependency in your `Package.swift`:

```swift
.package(
    url: "https://github.com/apple/swift-openapi-runtime",
    .upToNextMinor(from: "0.3.0")
),
```

Note that this repository does not have a 1.0 tag yet, so the API is not stable.

Next, in your target, add `OpenAPIRuntime` to your dependencies:

```swift
.target(name: "MyTarget", dependencies: [
    .product(name: "OpenAPIRuntime", package: "swift-openapi-runtime"),
],
```

The next step depends on your use case.

### Using Swift OpenAPI Generator for code generation

The generated code depends on types from this library. Check out the adoption guides in the [Swift OpenAPI Generator documentation][1] to see how the packages fit together.

### Implementing transports and middlewares

Swift OpenAPI Generator generates client and server code that is designed to be used with pluggable transports and middlewares.

Implement a new transport or middleware by providing a type that adopts one of the protocols from the runtime library:

* `ClientTransport`
* `ClientMiddleware`
* `ServerTransport`
* `ServerMiddleware`

You can also publish your transport or middleware as a Swift package to allow others to use it with their generated code.

## Reporting issues

Please report any issues related to this library in the [swift-openapi-generator](https://github.com/apple/swift-openapi-generator/issues) repository.

## Documentation

To learn more, check out the full [documentation][2].

[0]: https://github.com/apple/swift-openapi-generator
[1]: https://swiftpackageindex.com/apple/swift-openapi-generator/documentation
[2]: https://swiftpackageindex.com/apple/swift-openapi-runtime/documentation
