KeyGenerator
======

KeyGenerator is a [PBKDF2][] implementation for [Elixir][]. Conforming to [rfc2898][].

[PBKDF2]: http://en.wikipedia.org/wiki/PBKDF2
[Elixir]: http://elixir-lang.org
[rfc2898]: http://tools.ietf.org/html/rfc2898

## Usage

```elixir
defmodule User do
  def encrypt_password(password, salt, opts \\ []) do
    KeyGenerator.generate_key(password, salt, opts)
  end
end
{:ok, key} = User.encrypt_password("password", "salt", iterations: 4096, length:
20)
```
