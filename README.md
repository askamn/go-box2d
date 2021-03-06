# Box2D.go

## What is this ?
Original port - https://github.com/ByteArena/box2d

*I maintain this port because the original port has some bugs and no one seems to be maintaining it.*
*Pull Requests are welcome*

This is Go a port of Box2D (https://github.com/erincatto/Box2D), a 2D physics engine for games written in C++ by Erin Catto.

The port is complete and based on the latest Box2D commit as of 2017-09-20 (https://github.com/erincatto/Box2D/commit/f655c603ba9d83f07fc566d38d2654ba35739102)

## Documentation

http://box2d.org/manual.pdf

## API changes

The API had to change a tiny bit due to the fact that :

* Go has no constructors as a language feature, thus code for constructors has been placed in `Make$NAME_OF_TYPE` functions
* Go has no support for function overloading; some functions implemented multiple times for different sets of parameters under the same name in C++ are distinguished by name in the golang version; we tried to make names explicit so that should not be an issue
* Go has no support for operator overloading; this C++ feature is used extensively throughout the C++ version of Box2D (mainly for the vector and matrix arithmethic), and has been converted to good old, albeit verbose function calls

## Tests

No opengl testbed for the moment.

Our tests verify the output of position and rotation of bodies over time against those generared by the C++ reference.

Right now, there's a test (passing) checking all the supported body shape collisions in `cmd/test-character-collision`.

## Usage example

Have a look at `cpp_compliance_test.go`.

## License of the original Box2D (C++)

The original Box2D is developed by Erin Catto, and has the zlib license. Thank you Erin for this incredible piece of software.

## License of this port (Go)

zlib
