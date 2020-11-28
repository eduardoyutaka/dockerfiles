# Phoenix

Run a Phoenix application with Postgres from scratch using Docker.

```bash
$ mix phx.new my_app
$ cd my_app
```

Edit the `config/dev.exs` file to use the Postgres database running in the container.

```elixir
# Configure your database
config :my_app, MyApp.Repo,
  username: "postgres",
  password: "postgres",
  database: "my_app_dev",
  hostname: System.get_env("POSTGRES_HOST") || "localhost",
  show_sensitive_data_on_connection_error: true,
  pool_size: 10
```

Copy the `Dockerfile`, `docker-compose.yml` and `entrypoint.sh` files into your application directory.

```bash
$ cp /path/to/Dockerfile /path/to/my_app
$ cp /path/to/docker-compose.yml /path/to/my_app
$ cp /path/to/entrypoint.sh /path/to/my_app
```

Start the application.

```bash
$ docker-compose up
```
