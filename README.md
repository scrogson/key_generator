KeyGenerator
======

KeyGenerator is a [PBKDF2][] implementation for [Elixir][]. Conforming to [rfc2898][].

[PBKDF2]: http://en.wikipedia.org/wiki/PBKDF2
[Elixir]: http://elixir-lang.org
[rfc2898]: http://tools.ietf.org/html/rfc2898

## Usage

```elixir
defmodule User do
  import KeyGenerator

  def encrypt_password(password, salt, opts \\ []) do
    generate(password, salt, opts) |> to_hex
  end
end

key = User.encrypt_password("password", "salt")
# => "f87cbb89d972a9b96f5a9e2068308f06e1cf6421748..."
```

The available options are:

* `:iterations` - defaults to 1000.
* `:length` - derived key length. Defaults to 64.
* `:digest` - The `hmac` function to perform. Defaults to `:sha`.
