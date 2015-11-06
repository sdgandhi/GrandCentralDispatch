Kalopsia
========

[![Swift 2.0](https://img.shields.io/badge/Swift-2.0-orange.svg?style=flat)](https://developer.apple.com/swift/)
[![Platforms OS X | iOS](https://img.shields.io/badge/Platforms-OS%20X%20%7C%20iOS-lightgray.svg?style=flat)](https://developer.apple.com/swift/)
[![Carthage Compatible](https://img.shields.io/badge/Carthage-Compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![License MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat)](https://github.com/Carthage/Carthage)
[![Travis](https://img.shields.io/badge/Build-Passing-4BC51D.svg?style=flat)](https://travis-ci.org/Zewo/Kalopsia)
[![codecov.io](http://codecov.io/github/Zewo/Kalopsia/coverage.svg?branch=master)](http://codecov.io/github/Zewo/Kalopsia?branch=master)

**Kalopsia** is a Grand Central Dispatch wrapper for **Swift 2**.

## Features

- [x] No `Foundation` dependency (**Linux ready**)
- [x] Queues
- [x] Semaphore
- [x] IO Channel

## Installation

### Carthage

[Carthage](https://github.com/Carthage/Carthage) is a decentralized dependency manager that automates the process of adding frameworks to your Cocoa application.

You can install Carthage with [Homebrew](http://brew.sh/) using the following command:

```bash
$ brew update
$ brew install carthage
```

To integrate **Kalopsia** into your Xcode project using Carthage, specify it in your `Cartfile`:

```ogdl
github "Zewo/Kalopsia"
```

### Manually

If you prefer not to use a dependency manager, you can integrate **Kalopsia** into your project manually.

#### Embedded Framework

- Open up Terminal, `cd` into your top-level project directory, and run the following command "if" your project is not initialized as a git repository:

```bash
$ git init
```

- Add **Kalopsia** as a git [submodule](http://git-scm.com/docs/git-submodule) by running the following command:

```bash
$ git submodule add https://github.com/Zewo/Kalopsia.git
```

- Open the new `Kalopsia` folder, and drag the `Kalopsia.xcodeproj` into the Project Navigator of your application's Xcode project.

    > It should appear nested underneath your application's blue project icon. Whether it is above or below all the other Xcode groups does not matter.

- Select the `Kalopsia.xcodeproj` in the Project Navigator and verify the deployment target matches that of your application target.
- Next, select your application project in the Project Navigator (blue project icon) to navigate to the target configuration window and select the application target under the "Targets" heading in the sidebar.
- In the tab bar at the top of that window, open the "General" panel.
- Click on the `+` button under the "Embedded Binaries" section.
- You will see two different `Kalopsia.xcodeproj` folders each with two different versions of the `Kalopsia.framework` nested inside a `Products` folder.

    > It does not matter which `Products` folder you choose from, but it does matter whether you choose the top or bottom `Kalopsia.framework`.

- Select the top `Kalopsia.framework` for OS X and the bottom one for iOS.

    > You can verify which one you selected by inspecting the build log for your project. The build target for `Kalopsia` will be listed as either `Kalopsia iOS` or `Kalopsia OSX`.

- And that's it!

> The `Kalopsia.framework` is automagically added as a target dependency, linked framework and embedded framework in a copy files build phase which is all you need to build on the simulator and a device.

License
-------

**Kalopsia** is released under the MIT license. See LICENSE for details.