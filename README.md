# Pinata 🪅
[![Build Status](https://github.com/m1ome/ex_pinata/workflows/tests/badge.svg)](https://github.com/m1ome/ex_pinata/actions)
[![hex.pm version](https://img.shields.io/hexpm/v/ex_pinata.svg)](https://hex.pm/packages/ex_pinata)
[![hex.pm downloads](https://img.shields.io/hexpm/dt/ex_pinata.svg)](https://hex.pm/packages/ex_pinata)
[![License](https://img.shields.io/hexpm/l/exvcr.svg)](http://opensource.org/licenses/MIT)

Adapter for [pinata.cloud](https://www.pinata.cloud/)

## Installation
Add `ex_pinata` to your dependencies in `mix.exs`.
```elixir
def deps do
  [
    {:ex_pinata, "~> 1.0.1"}
  ]
end
```

Add `ex_pinata` as an extra application in `mix.exs`.
```elixir
def application do
    [
      extra_applications: [
        :logger,
        :ecto,
        ...
        :ex_pinata,
        ...
        :telemetry,
      ],
      mod: {MyApp, []}
    ]
  end
```

To start using the adapter you need to provide config from Pinata:
```elixir
config :ex_pinata,
  api_key: "YOUR_PINATA_API_KEY",
  api_token: "YOUR_PINATA_API_KEY
```

## Usage 
```elixir
content = File.read!("/path/to/some/file")
{:ok, file} = Pinata.pin_file(content, "my_file")
```