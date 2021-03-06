Dalton
======

[![Pod](https://img.shields.io/cocoapods/v/Dalton.svg)](http://cocoapods.org/pods/Dalton)   [![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage) [![Build Status](https://img.shields.io/travis/dcaunt/Dalton.svg)](https://travis-ci.org/dcaunt/Dalton)

A simple RSS & Atom feed parser, built upon [Ono](https://github.com/mattt/Ono).

Requires Xcode 6.

## Usage

Parsing feeds is simple. You don't need to know ahead of time whether you're parsing an RSS or Atom feed, and Dalton abstracts away the differences.

```objective-c
NSError *error = nil;
NSURL *fileURL = [[NSBundle mainBundle] URLForResource:@"sample" withExtension:@"xml"];
NSData *feedData = [NSData dataWithContentsOfURL:fileURL];
id<DLTFeed> feed = [DLTFeed feedWithData:feedData error:&error];

NSLog(@"Feed title is %@", feed.title);
NSLog(@"Feed was last updated at %@", feed.updated);
for (id<DLTFeedEntry> entry in feed.entries) {
    NSLog(@"Entry title is %@ link is %@", entry.title, entry.link);
}
```

## Installation

Dalton supports both [CocoaPods](https://cocoapods.org/) and [Carthage](https://github.com/Carthage/Carthage).

### CocoaPods

Add Dalton to your `Podfile`
```
pod 'Dalton'
```

### Carthage

Carthage is supported from version 0.0.3 onwards. Add Dalton to your `Cartfile`.
```
github "dcaunt/Dalton"
```

## Contact 

[@dcaunt](https://twitter.com/dcaunt)

## License

MIT. See [LICENSE](https://github.com/dcaunt/Dalton/blob/master/LICENSE) for more details.
