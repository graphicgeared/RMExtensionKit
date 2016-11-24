# RMExtensionKit

[![CI Status](http://img.shields.io/travis/rondinellimorais/RMExtensionKit.svg?style=flat)](https://travis-ci.org/rondinellimorais/RMExtensionKit)
[![Version](https://img.shields.io/cocoapods/v/RMExtensionKit.svg?style=flat)](http://cocoapods.org/pods/RMExtensionKit)
[![License](https://img.shields.io/cocoapods/l/RMExtensionKit.svg?style=flat)](http://cocoapods.org/pods/RMExtensionKit)
[![Platform](https://img.shields.io/cocoapods/p/RMExtensionKit.svg?style=flat)](http://cocoapods.org/pods/RMExtensionKit)

## Overview
RMExtesionKit is simple structure that contains the extension methods that simplifies the use of cocoa classes iOS / OSX.

Here are some classes that contains several useful extensions:

- #### String
	+ Properties
		* empty
		* length

	+ Methods
		* toArray
		* substring
		* test (regex)
		* encodeURIComponent
		* toHTML
		* toDictionary
		* anymore...

- #### UITableView
	+ methods
		* rowHeight (base on cell identifier)

- #### UIView
	+ methods
		* showBorder
		* toImage
		* loadNibView

- #### Date
	+ properties
		* isToday

	+ methods
		* addSeconds
		* addHours
		* timeInterval
		* compareTo
		* differecesDay (in days)
		* init(year, month, day, hour, minute, second)
		* anymore...

## CocoaPods

[CocoaPods](http://cocoapods.org) is a dependency manager for Swift and Objective-C, which automates and simplifies the process of using 3rd-party libraries like RMExtensionKit in your projects. You can install it with the following command:

```bash
$ gem install cocoapods
```

#### Podfile

RMExtensionKit is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '9.0'

target 'TargetName' do
pod 'RMExtensionKit'
end
```

## Usage Extensions

#### NSDate

Create simple date
```swift
let birthDate = Date(year: 1987, month: 10, day: 08)
print(birthDate)
```

Get time internal
```swift
let birthDate = Date(year: 1987, month: 10, day: 08)
print(birthDate.timeInterval())
```
Date format
```swift
let birthDate = Date(year: 1987, month: 10, day: 08)
print(birthDate.toString("yyyy/MM/dd"))
```

#### NSURLConnection

Check if internet is connected
```swift
if NSURLConnection.isConnectedToNetwork() {
  print("Yes! Connected!")
}
```

#### String

JSON String to dictionary
```javascript
{
  "array": [
    1,
    2,
    3
  ],
  "boolean": true,
  "null": null,
  "number": 123,
  "object": {
    "a": "b",
    "c": "d",
    "e": "f"
  },
  "string": "Hello World"
}
```

```swift
let JSONString = "{\"array\":[1,2,3],\"boolean\":true,\"null\":null,\"number\":123,\"object\":{\"a\":\"b\",\"c\":\"d\",\"e\":\"f\"},\"string\":\"Hello World\"}"
        print( JSONString.toDictionary() )
```

Bind HTML text
```swift
let htmlString = "<span style='color:red'>Hello world!</span><br/><span>This is a simple HTML text. This is <b>bold!</b></span>"
self.htmlTextLabel.attributedText = htmlString.toHTML()
```

Replace with regex
```swift
print("My password is: 12345678".replace("\\d", newValue: "*") )
```

See documentations for anymore!

## Author

Rondinelli Morais, rondinellimorais@gmail.com

## License

RMExtensionKit is available under the MIT license. See the LICENSE file for more info.
