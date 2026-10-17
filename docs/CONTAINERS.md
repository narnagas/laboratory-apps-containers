# Angular container laboratory

## Prerequisites

Docker Engine/Desktop with Compose v2.17+ and BuildKit; two sibling checkouts:

```text
workspace/
  laboratory-apps/
  laboratory-apps-containers/
```

## Run

From `laboratory-apps-containers`:

```bash
docker compose up --build -d
docker compose ps
docker compose down
```

Browse `http://localhost:8088`. The container builds the Angular app from the sibling source checkout, then serves static output via Nginx. The Dockerfile and Nginx configuration remain in this repository.

## Scope

This is a **local container proof of concept**, not the IIS deployment mechanism. The Azure DevOps pipeline will initially deploy static Angular build artifacts to IIS directly. No credentials or private keys are needed here.
