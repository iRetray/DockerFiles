# Doméstica

## Build app with Docker

```sh
docker build ./ --tag frontend_builder
mkdir ./dist
docker run --rm --volume "$PWD/dist:/app/dist" frontend_builder
```

## Tauri docs

### Conexión con servicios en RUST

- [Metodos para REST API (event)](https://tauri.studio/docs/api/js/modules/event)
- [Peticiones GET (invoke)](https://tauri.studio/docs/api/js/modules/tauri/#invoke)
- [Repositorio de ejemplo](https://github.com/tauri-apps/tauri/tree/dev/examples/api/src/components)
