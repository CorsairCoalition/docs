# Installation
## Prerequisites

- [Docker](https://docs.docker.com/engine/install)
- [Docker Compose](https://docs.docker.com/compose/install)

Use the following commands to test:

```sh
$ docker version
$ docker compose version
```

## Usage

1. Grab the latest `gg-framework.zip` from [releases](https://github.com/CorsairCoalition/docs/releases) and extract the contents.

2. Navigate to the newly created "gg-framework" directory:

```sh
$ cd path/to/gg-framework
```

3. Make a copy of the example configuration file, `config.json.example` and change the `userId`, `username`, and other variables as desired.

```sh
$ cp config.json.example config.json
$ sed -i "s/RANDOMLY_GENERATED_STRING/$(openssl rand -base64 12)/" config.json
```

4. Run background services.

```sh
$ docker compose up
```

Note: This command will start the Docker container that hosts the GG framework components: [SergeantSocket](https://github.com/CorsairCoalition/SergeantSocket), [ArmadaAssault](https://github.com/CorsairCoalition/ArmadaAssault), [Redis](https://redis.io/). You may see a series of warnings as Redis starts; these can be safely ignored.

4. When you see "READY TO PLAY", continue to the next step.

5. Open a new terminal window and navigate to the same "gg-framework" directory.

6. Execute the following command:

```sh
$ docker compose run commander-cortex
```

The Commander Cortex UI should appear. You are now ready to use the pre-configured bot in the GG framework.

## Gameplay Analysis

See [README.ipynb](README.ipynb) for further details.
