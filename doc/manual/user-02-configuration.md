\newpage

# Configuration

The configuration is loaded from either the path specified by the `-c` flag or `/etc/pgprtdbg/pgprtdbg.conf`.

The configuration of [**pgprtdbg**][pgprtdbg] is split into sections using the `[` and `]` characters.

The main section, called `[pgprtdbg]`, is where you configure the overall properties of [**pgprtdbg**][pgprtdbg].

Other sections doesn't have any requirements to their naming so you can give them meaningful names like `[primary]` for the primary [PostgreSQL][postgresql] instance.

All properties are in the format `key = value`.

The characters `#` and `;` can be used for comments; must be the first character on the line.

The `Bool` data type supports the following values: `on`, `yes`, `1`, `true`, `off`, `no`, `0` and `false`.

See a [sample][sample] configuration for running [**pgprtdbg**][pgprtdbg] on `localhost`.

## [pgprtdbg]

| Property              |Default|Unit  |Required| Description |
|-----------------------|-------|------|--------|-------------|
| host | | String | Yes | The bind address for pgprtdbg |
| port | | Int | Yes | The bind port for pgprtdbg |
| output | | String | Yes | The output location |
| unix_socket_dir | | String | No | The Unix Domain Socket directory |
| log_type | console | String | No | The logging type (console, file) |
| log_path | pgprtdbg.log | String | No | The log file location |
| output_sockets | off | Bool | No | Output socket descriptors |
| save_traffic | off | Bool | No | Save the traffic in files |
| libev | `auto` | String | No | Select the [libev](http://software.schmorp.de/pkg/libev.html) backend to use. Valid options: `auto`, `select`, `poll`, `epoll`, `linuxaio`, `iouring`, `devpoll` and `port` |
| buffer_size | 65535 | Int | No | The network buffer size (`SO_RCVBUF` and `SO_SNDBUF`) |
| keep_alive | on | Bool | No | Have `SO_KEEPALIVE` on sockets |
| nodelay | off | Bool | No | Have `TCP_NODELAY` on sockets |
| backlog | 4 | Int | No | The backlog for `listen()` |

## Server section

| Property       | Default | Unit | Required | Description |
|----------------|---------|------|----------|-------------|
| host | | String | Yes | The address of the PostgreSQL instance |
| port | | Int | Yes | The port of the PostgreSQL instance |
