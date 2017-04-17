# WebSockex

An Elixir Websocket Client.

The client itself is provided through the `WebSockex.Client` module.

The simplest implemenation is

```elixir
defmodule WebSocketExample do
  use WebSockex.Client

  def start_link(url, state) do
    WebSockex.Client.start_link(url, __MODULE__, state)
  end

  def handle_frame({type, msg}, state) do
    IO.puts "Recieved Message - Type: #{inspect type} -- Message: #{inspect msg}"
  end
end
```

See the `examples/` directory for other examples or take a look at the [documentation][docs].

## Installation

1. Add `websockex` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [{:websockex, "~> 0.1.0"}]
end
```

2. Ensure `websockex` is started before your application:

```elixir
def application do
  [applications: [:websockex]]
end
```

[docs]: https://hexdocs.pm/websockex
