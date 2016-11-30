# Telegram CLI docker container
This is a container with the prebuild of the telegram-cli based on the new tglib. (See [Release Page](https://valtman.name/telegram-cli).)

The Telegram CLI listens at port `4458`.


### Build a docker with a specific version:

In this example build `1124`. See the links at https://valtman.name/telegram-cli for the latest.

```shell
export TGCLI_VERSION=1124 && docker build .  -t luckydonald/tg-cli:${TGCLI_VERSION}
```

### Run a docker

```sh
docker run -it --rm --name=tg_cli -v "/docker-data/telegram-cli:/telegram/data" luckydonald/tg-cli:1124
```

The data will be stored in `/telegram/data/`. This is set in the `configfile.txt` and the `--config /telegram/config` parameters.
The `-v` flag let the `/telegram/data/` from inside the container be the server's (host computer's) `/docker-data/telegram-cli/`.

If you prefer using the `docker-compose.yml` file instead, you can run:

```sh
docker-compose up
```

