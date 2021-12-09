# Elixir TDLib

This elixir library binds [telegram's
TDLib](https://core.telegram.org/tdlib), allowing you to interact with
Telegram as a full-fledged client (not as a bot!). It ships :

* [Telegram's tdlib](https://github.com/tdlib/td), licensed under the Boost
  Software License 1.0 (BSL-1.0)
* [oott123's tdlib-json-cli](https://github.com/oott123), licensed under the
  GNU Affero General Public License v3.0 (AGPL-3.0)

Most of the interactions with this project are done via the `TDLib` module. Any
structure used to interact with TDLib is defined under either `TDLib.Object` or
`TDLib.Method`. You can create as many session as you want, but note that each
of them launch a new instance of tdlib-json-cli via a
[port](https://hexdocs.pm/elixir/Port.html).

# Installation

Add the following to your `mix.exs` :

```
def deps do
  [{:tdlib, "~> 0.0.1"}]
end
```

Note that compiling this project will compile Telegram's TDLib (C++) itself,
it's going to take a while and depends on the following :

 * C++14 compatible compiler (clang 3.4+, GCC 4.9+, MSVC 19.0+ (Visual Studio
   2015+), Intel C++ Compiler 17+)
 * OpenSSL
 * zlib
 * gperf
 * CMake (3.0.2+)

# Configuration

This library **do not need** configuration, however, the following options are
available :

```
# Disable automatic handling of authentification and directly forward the
# incoming messages to the client
config :telegram_tdlib, disable_handling: false

# Override default path of the telegram-json-cli binary
config :telegram_tdlib, backend_binary: "/path/to/my/binary"
```

# Usage / Example

Long Time No UPDATE!
A simple example can be found at
[gitlab.com/Fnux/elixir-tdlib-demo](https://gitlab.com/Fnux/elixir-tdlib-demo).
Please refer to the `TDLib` module for proper documentation.
