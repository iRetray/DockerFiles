# Backend Rust app

## Prepare enviroment

- Install [Rust](https://www.rust-lang.org/tools/install)
- Download the **Docker Image** for _MongoDB 5.0.7_

```sh
docker pull mongo:5.0.7
```

- Run the **MongoDB docker container:**

```sh
docker run -it --rm -e MONGO_INITDB_ROOT_USERNAME=SergioRibera -e MONGO_INITDB_ROOT_PASSWORD=SergioRibera -e MONGO_INITDB_DATABASE=MiDo_BackOffice -p 27018:27017 -v "$PWD/mongo-init.js:/docker-entrypoint-initdb.d/mongo-init.js:ro" mongo:5.0.7
```

- Install [Tauri](https://tauri.studio/docs/getting-started/setting-up-linux/?fbclid=IwAR3l8ciuyUTF93tGIl_NYBHN5Nrxt4uj2aiHhrA0bX87aRYriACRXlBx0LI)

## Run with Docker

To build the tauri image, you need run this command
```sh
docker build -t tauri_builder:latest .
```

To build with tauri image, you need run the next command
```sh
docker run --rm -u "$(id):$(id -g)" -v "$(pwd):/app" -w "/app" tauri_builder:latest cargo build
```

To run this binary file, you only need run the binary generated on `target/debug/app`

```sh
./target/debug/app
```
