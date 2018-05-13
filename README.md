# reason-native

After a few conversation during Reason Conf it seems like there's an interest in the topic and there are already some libraries that could help make it happen.

The goal of this repo is to gather ideas and set some kind of rough road map of what we need to achieve it.

## Roadmap

TBD

## Libraries

- [Flex](https://github.com/jordwalke/flex) 
- [bsb-native](https://github.com/bsansouci/bsb-native)
- [BriskML](https://github.com/briskml/brisk)
- and there are probably more so feel free to fill this up

## Resources

- [Compile OCaml for iOS](http://psellos.com/ocaml/compile-to-iphone.html)
- [What does reason + react native look like?](https://github.com/facebook/reason/issues/658)

## Thoughts

### [@jaredly](https://github.com/jaredly):
Lots of people have asked about reason-react compiled to native (Reason Native React Native or RNRN 😎), here's a rough outline of dependencies that have to fall into place.

#### Prerequisites
status: in progress

The main thing here is getting a package manager + build toolchain that make cross-compilation a breeze. @jordwalke and some others are working on this right now, and it's called [esy](https://github.com/esy/esy).

Time remaining before it's usable: 2-8 months? :P [TODO put in a better estimate about timeline]

##### Potential direction #1
status: not started

Use existing react-native infrastructure, and make a reason-react implementation that talks the same protocol as react-native currently uses.

Benefits: we can re-use all the flex-box, native view bindings, etc. that react-native already has.
Downsides: that might come with some cruft as well.

##### Potential direction #2
status: started (repo [here](https://github.com/briskml/brisk))

Create a new implementation of React that's especially for Reason + Native
- based off of [ReactMini](https://github.com/reasonml/reason-react/tree/master/ReactMini)
- also using code from [Reason Flex](https://github.com/jordwalke/flex)
- currently prototyped with bindings for iOS
- hasn't started into the Android side yet

Benefits: very tight implementation, light weight
Downsides: have to do new bindings to Android, iOS APIs
