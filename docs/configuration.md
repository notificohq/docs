# Configuration

## Configuration variables

All these variables can be passed to executables as command-line arguments (see `--help` for more information), as environment variables, or in `.env` file.

| Environment variable      | Required         | Description                                                                                                                                  |
|---------------------------|------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| NOTIFICO_DB               | :material-check: | Database URL used as persistent data storage. <br/>Notifico supports SQLite, PostgreSQL, MySQL (MariaDB) and their derivatives.              |
| NOTIFICO_SECRET_KEY       | :material-check: | Secret key, used for various needs. Mainly, for creating JWT tokens. Can be any printable sequence.                                          |
| NOTIFICO_AMQP             |                  | AMQP broker URL address. Virtual hosts are currently not supported. **Example**: `amqp://guest:guest@127.0.0.1` for local RabbitMQ instance. |
| NOTIFICO_AMQP_PREFIX      |                  | AMQP queue prefix.                                                                                                                           |
| NOTIFICO_HTTP_INGEST_BIND |                  | Local address for [ingest](components.md#ingest) service.                                                                                    |
| NOTIFICO_UI_BIND          |                  | Local address for [web](components.md#web) service.                                                                                          |
| NOTIFICO_PUBLIC_BIND      |                  | Local address for [userapi](components.md#user-api) service.                                                                                 |
| NOTIFICO_PUBLIC_URL       |                  | User-facing address for userapi service                                                                                                      |

## Credentials

Credentials in Notifico are set using environment variables. The format for setting credentials is as follows:

```shell
NOTIFICO_CRED_<NAME>=<TRANSPORT>:<VALUE>
```

Where:

- `<NAME>` is the name of the credential. This name is converted into lowercase.
- `<TRANSPORT>` is the transport name
- `<VALUE>` is the actual credential value

For more detailed information about credential formats and their usage with specific plugins, please refer to the [Plugins](plugins/core.md) section of the documentation.
