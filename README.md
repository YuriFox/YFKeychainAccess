# YFKeychainAccess

[![platform](https://img.shields.io/badge/Platform-iOS%208%2B-blue.svg)]()
[![language](https://img.shields.io/badge/Language-Swift-red.svg)]()
[![language](https://img.shields.io/badge/pod-4.0.0-blue.svg)]()
[![license](https://img.shields.io/badge/license-MIT-lightgray.svg)]()

Convenient, beautiful and easy to use KeychainAccess, that written in Swift

- [Requirements](#requirements)

- [Installation](#installation)
    - [CocoaPods](#CocoaPods)
    - [Manually](#Manually)
    
- [Usage](#usage)
    - [Set](#Set)
    - [Get](#Get)
    - [Delete](#Delete)
    - [Contains](#Contains)
    
- [License](#license)

## Requirements

- iOS 8.0+
- Xcode 9.0+
- Swift 4.0+

## Installation
### CocoaPods

[CocoaPods](http://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:

```bash
$ gem install cocoapods
```

- Create `Podfile` into your Xcode project. Open up `Terminal` → `cd` into your project's top-level directory → Run the following command:

```bash
$ pod init
```

- Open up created  `Podfile`.

```bash
$ open Podfile
```

- In the `Podfile` that appears, specify. Instead of `<Your Target Name>`, enter your project's name :

```ruby
platform :ios, ‘8.0’

target '<Your Target Name>' do
    use_frameworks!
	pod 'YFKeychainAccess'
end
```

- Then, run the following command:

```bash
$ pod update
$ pod install
```

- Finally, open your Xcode  `<Your Target Name>.xcworkspace`.

## Usage

```swift
import YFKeychainAccess
```
### Set

```swift
let keychain = YFKeychainAccess() // You can add 'keyPrefix' and 'options' to customize KeychainAccess

do {
    try keychain.set(value, forKey: "KEY") // You can add 'accessible' parameter too
    // 'set' function update item or creates a new one
} catch {
    // Handle error if necessary
}
```

### Get

```swift
let keychain = YFKeychainAccess() // You can add 'keyPrefix' and 'options' to customize KeychainAccess

do {
    let data = try keychain.data(forKey: "DATA_KEY")
    let string = try keychain.string(forKey: "STRING_KEY")
    let bool = try keychain.bool(forKey: "BOOL_KEY")
    let int = try keychain.(forKey: "INT_KEY")
    let float = try keychain.float(forKey: "FLOAT_KEY")
    let double = try keychain.double(forKey: "DOUBLE_KEY")
} catch {
    // Handle error if necessary
}
```

### Delete

```swift
let keychain = YFKeychainAccess() // You can add 'keyPrefix' and 'options' to customize KeychainAccess

do {
    try keychin.delete(forKey: "KEY") // Delete one item for key
    try keychin.deleteAll() // Delete all item for this app
} catch {
    // Handle error if necessary
}
```

### Contains

```swift
let keychain = YFKeychainAccess() // You can add 'keyPrefix' and 'options' to customize KeychainAccess

do {
    try keychin.contains(forKey: "KEY")
} catch {
    // Handle error if necessary
}
```

## License
Released under the MIT license. See [LICENSE](https://github.com/YuriFox/YFKeychainAccess/blob/1.0/LICENSE) for details.
