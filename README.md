# La Laguna Tek — Laboratory Containers

Docker and Compose infrastructure for [`laboratory-apps`](https://github.com/narnagas/laboratory-apps).

## Angular local proof of concept

Clone both repositories into sibling directories, then run `docker compose up --build -d` in this repository. Browse `http://localhost:8088`. See [container instructions](docs/CONTAINERS.md).

## Git flow

`feature/*` → `development` → `main`, through reviewed pull requests.

Do not commit secrets, production data or private certificates. IIS deployment is a separate Azure Pipelines milestone.
