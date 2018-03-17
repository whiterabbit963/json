# The Art of C++ / JSON

[![Release](https://img.shields.io/github/release/taocpp/json.svg)](https://github.com/taocpp/json/releases/latest)
[![TravisCI](https://travis-ci.org/taocpp/json.svg)](https://travis-ci.org/taocpp/json)
[![AppVeyor](https://ci.appveyor.com/api/projects/status/github/taocpp/json?svg=true)](https://ci.appveyor.com/project/taocpp/json)
[![Coverage](https://img.shields.io/coveralls/taocpp/json.svg)](https://coveralls.io/github/taocpp/json)

The Art of C++ / JSON is a zero-dependency C++11 header-only library that provides a generic [JSON Value class](doc/Value-Class.md) and a generic [JSON Events interface](doc/Events-Interface.md).
A [traits mechanism](doc/Type-Traits.md) allows integration of (custom) C++ types and efficient conversions from and to the Value class and multiple JSON representation formats.
It is designed for correctness and simplicity, is based on C++ standard containers, and strives for speed through minimalism (rather than complicated optimisations).

## Documentation

* [Documentation](doc/README.md)

## Features

* Standards

  * [RFC7159], [ECMA-404]: The JavaScript Object Notation (JSON) Data Interchange Format.
  * Achieves a **100%** conformance score in the [Native JSON Benchmark] tests.
  * [RFC6901]: JavaScript Object Notation (JSON) Pointer.
  * [RFC6902]: JavaScript Object Notation (JSON) Patch.
  * [RFC7049]: Concise Binary Object Representation ([CBOR]).
  * [JAXN]: Relaxed JSON with binary data and non-finite numbers.
  * [MsgPack]: MessagePack binary format (without extensions).
  * [UBJSON]: Universal Binary JSON.

* [JSON Value Class](doc/Value-Class.md)

  * Construction of objects and arrays via `std::initializer_list`.
  * Conversion from and to arbitrary *custom types* via [traits class template](doc/Type-Traits.md).
  * Built around STL containers `std::string`, `std::map` and `std::vector`.
  * No memory allocations by the JSON Value class itself (the wrapped containers allocate normally).
  * Instance sharing for string, binary, JSON Value, and *custom types* via non-owning pointers.
  * C++11 literal operator for JSON Values, including binary data.
  * Optional custom annotations for all Values (e.g. [filename and line (sub-)values were parsed from](doc/Advanced-Use-Cases.md#annotate-with-filename-and-line-number).

* [JSON Events Interface](doc/Events-Interface.md)

  * Simple, straightforward and flexible JSON Events API.
  * JSON Events-to-Value and Value-to-Events interfaces.
  * Parse JSON & JAXN string representation to JSON Events.
  * Stream JSON Events to (prettified) JSON & JAXN string representation.
  * Conversion from and to binary formats, currently [CBOR], [UBJSON], [MsgPack].
  * Conversion from and to *other* JSON libraries (e.g. [`contrib/nlohmann.cpp`](contrib/nlohmann.cpp)).
  * JSON Events comparison, hashing, counting, and schema validation.
  * JSON Events filters to manipulate Events in various ways.

## Status

The library is stable as in "works correctly" over months of multiple real-world applications.

The library is not stable as in "under construction"; some parts of the API are under discussion and development and might change and/or be extended before version 1.0.

This library also serves as a real-world example application of the [Parsing Expression Grammar Template Library (PEGTL)], which is used for parsing the JSON and JAXN representation formats.

## License

The Art of C++ / JSON is certified [Open Source] software. It may be used for any purpose, including commercial purposes, at absolutely no cost. It is distributed under the terms of the [MIT license] reproduced here.

> Copyright (c) 2015-2018 Dr. Colin Hirsch and Daniel Frey
>
> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Contact

For questions and suggestions about the Art of C++ / JSON please contact the authors at `taocpp(at)icemx.net`.

## Thank You

* Niels Lohmann and his [JSON library](https://github.com/nlohmann/json) for the inspiration.
* Milo Yip and his [Native JSON Benchmark] for a reference to measure progress against.

## Additional Licenses

The Art of C++ / JSON contains slightly modified portions of the [double-conversion library](https://github.com/google/double-conversion) which is licensed as follows:

> Copyright 2006-2011, the V8 project authors. All rights reserved. Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:
>
> * Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
> * Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
> * Neither the name of Google Inc. nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.
>
> THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

[CBOR]: http://cbor.io
[ECMA-404]: http://www.ecma-international.org/publications/standards/Ecma-404.htm
[JAXN]: https://github.com/stand-art/jaxn
[JSON Reference]: https://tools.ietf.org/html/draft-pbryan-zyp-json-ref-03
[JSON Schema]: http://json-schema.org/documentation.html
[MsgPack]: http://msgpack.org
[MIT license]: http://www.opensource.org/licenses/mit-license.html
[Native JSON Benchmark]: https://github.com/miloyip/nativejson-benchmark
[Open Source]: http://www.opensource.org/docs/definition.html
[Parsing Expression Grammar Template Library (PEGTL)]: https://github.com/taocpp/PEGTL
[RFC6901]: https://tools.ietf.org/html/rfc6901
[RFC6902]: https://tools.ietf.org/html/rfc6902
[RFC7049]: https://tools.ietf.org/html/rfc7049
[RFC7159]: https://tools.ietf.org/html/rfc7159
[UBJSON]: http://ubjson.org
