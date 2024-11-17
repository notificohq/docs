# Configuration

## Configuration variables

All these variables can be passed to executables as command-line arguments (see `--help` for more information), as environment variables, or in `.env` file.

- `NOTIFICO_DB_URL` **(required)**: Database URL used as persistent data storage.
Notifico supports SQLite, PostgreSQL, MySQL (MariaDB) and their derivatives.  
**Example:** `sqlite://db.sqlite3`
- `NOTIFICO_SECRET_KEY` **(required)**: Secret key, used for various needs. Mainly, for creating JWT tokens. Can be any printable sequence.
- `NOTIFICO_AMQP_URL` **(required)**: AMQP broker URL address. Virtual hosts are currently not supported.  
**Example:** `amqp://guest:guest@127.0.0.1` for local RabbitMQ instance
- `NOTIFICO_SERVICE_API_BIND`: Local address  
**Default:** `[::]:8000`
- `NOTIFICO_CLIENT_API_BIND`=[::]:9000
- `NOTIFICO_CLIENT_API_URL`=http://localhost:9000/
- `NOTIFICO_CREDENTIALS_PATH`=credentials.toml

## Credentials

Credentials are stored in TOML format. You can add as many configurations as you need for different services.

See channels documentation for credential format.
