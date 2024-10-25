```
mix archive.install hex phx_new
mix phx.new app

cd app

sudo dnf install erlang-public_key

```

# mix.exs
```
defp deps do
  [
    {:mint, "~> 1.6"},
    {:finch, "~> 0.19.0"}
  ]
end
```

```
rm mix.lock
mix deps.compile
```

# config/dev.exs
```
config :your_app, YourApp.Repo,
  username: "postgres",
  password: "your_password",  # Replace with actual password
  database: "your_database_name",
  hostname: "localhost",
  pool_size: 10
```

```
mix deps.clean --all
mix deps.get
mix ecto.create  # Ensure the database is created
mix ecto.migrate # Run any pending migrations
iex -S mix phx.server
```