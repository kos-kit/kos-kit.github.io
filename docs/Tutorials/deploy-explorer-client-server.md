---
sidebar_position: 2
---

# Tutorial: deploy the KOS Kit Explorer in a client-server configuration with Docker

The tutorial will guide you in deploying the KOS Kit Explorer in a client-server configuration with Docker.

You can use this deployment method for large datasets such as [AGROVOC](https://agrovoc.fao.org/), which has tens of thousands of concepts.

### Before you start

Make sure you have [Docker](https://docs.docker.com/engine/install/) and [Docker Compose](https://docs.docker.com/compose/) installed.

### Copy the template GitHub repository

Follow [these instructions](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) on creating a GitHub repository from a template, using [this template repository](https://github.com/kos-kit/agrovoc-template).

### (Optional) Adapt the `docker-compose.yml`

You may want to:

- Change the container names and corresponding `environment` variables
- Change the ports
- Change the server `volumes` to point to a different host directory

### Copy your SKOS taxonomy files to `./release`

The `server` container expects to find your SKOS taxonomy in one or more files in `./release`.

Every RDF file should have the appropriate file extension e.g., `.nt` for N-Triples, `.ttl` for Turtle, et al.

### Start the servers

```
docker compose up
```

will start the KOS Kit Explorer on port 8080 and the KOS Kit Server on port 8081.

On startup, the KOS Kit Server loads the files in `./release` into a triple store and indexes them for fulltext search. The Explorer accesses the triple store via SPARQL and search via a custom HTTP interface.

### Open a browser

You should now be able to browse your taxonomy at [http://localhost:8080](http://localhost:8080).
