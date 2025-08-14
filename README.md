# docker-openwebui

Simple docker compose configuration to run private local Ollama service with Open WebUI

## Prerequisite

1.  install Ollama on your PC/mac <https://ollama.com/download/>
2.  start ollama and pull beloved image (llama3.1:8b, qwen3:8b)
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

5.  Open <http://localhost:3001/>
