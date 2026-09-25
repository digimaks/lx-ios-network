# NetworkWrapperPackage

Networking layer for iOS, built on Moya, with automatic token refresh.

It is one of the Swift packages used by **Digimaks**, a mobile digital wallet
continuing the work of the
[NOBID Consortium](https://www.nobidconsortium.com/) (the Nordic-Baltic eID
Project), one of the EU Large Scale Pilots preparing for eIDAS 2.0.

## Background

This package is the continuation of
[nobid-lsp-latvia/lx-ios-network](https://github.com/nobid-lsp-latvia/lx-ios-network),
developed within the NOBID Consortium and carried forward under the name
**Digimaks**.

## Requirements

- iOS 15+
- Swift 5.9+ / Xcode 15+

## Installation

Add the package to your `Package.swift`:

```swift
.package(url: "<repository-url>", from: "1.0.0")
```

or add it in Xcode via **File → Add Package Dependencies…**.

## Overview

| Type | Responsibility |
| ---- | -------------- |
| `RefreshbleMoyaProvider` | A `MoyaProvider` that transparently refreshes an expired access token and retries the request |
| `CommonServiceManagerProtocol` | Hook for the host app to react to unauthorised (401/403) and critical (500) responses |

Responses are surfaced to the host through the delegate, so session expiry and
server faults can be handled in one place.

## Dependencies

- [Moya](https://github.com/Moya/Moya)

## Licence

Licensed under the [EUPL-1.2](LICENSE). See [Notice](Notice) for attribution.
