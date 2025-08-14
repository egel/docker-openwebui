# docker-openwebui

Simple docker compose configuration to run private local Ollama service with Open WebUI

## Prerequisite

1.  install ollama on your pc/mac <https://ollama.com/download/>
2.  start ollama and pull beloved image ([llama3.1:8b](https://ollama.com/library/llama3.1), [qwen3:8b](https://ollama.com/library/qwen3))
3.  create `.env` by using `.env.example` and adjust the values

    ```sh
    cp .env.example .env
    ```

    > [!TIP]
    > Generate new random password with
    >
    > ```sh
    > openssl rand -base64 20
    > ```

4.  start docker compose

    ```sh
    docker compose up -d
    ```

5.  open <http://localhost:3001/>
