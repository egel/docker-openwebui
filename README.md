# docker-openwebui

Simple docker compose configuration to run private local Ollama service with Open WebUI

## Prerequisite

1.  install ollama on your pc/mac <https://ollama.com/download/>
2.  start ollama and pull beloved image ([llama3.1:8b](https://ollama.com/library/llama3.1), [qwen3:8b](https://ollama.com/library/qwen3))

## Setup

1.  create `.env` by using `.env.example` and adjust the values

    ```sh
    cp .env.example .env
    ```

    > [!TIP]
    > Generate new random password with
    >
    > ```sh
    > openssl rand -base64 20
    > ```

2.  start docker compose

    ```sh
    docker compose up -d
    ```

3.  open <http://localhost:3001/>

### Extra

If you want to quickly start the container or update with latest version, add below commands to your shell file, reload shell (e.g.: `source ~/.zshrc`) and use:

```sh
function startOpenWebui() {
    echo "Starting OpenWebUI within docker container"
    (
        cd ~/privatespace/github.com/egel/docker-openwebui  \
            && docker compose up -d \
            && echo "Running on: http://localhost:3001/" \
    )
}

function updateOpenWebui() {
    echo "Begin updating OpenWebUI docker image"
    (
        cd ~/privatespace/github.com/egel/docker-openwebui  \
            && docker compose stop \
            && docker compose down \
            && docker compose pull \
            && docker compose up -d --force-recreate --remove-orphans \
            && echo "Running on: http://localhost:3001/" \
    )
}
```
