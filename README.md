# DAppNodePackage-immich
Dappnode Immich package - Self-hosted photo and video management solution

The shared upstream-bump workflow tracks `immich-app/immich` and updates both
Immich services through `IMMICH_VERSION`. Review each proposed update against
the matching upstream release notes and Compose file before merging. Valkey and
Postgres remain pinned in `docker-compose.yml` and must be reviewed alongside
Immich updates; do not automatically upgrade the Postgres major version against
an existing data volume.

Immich's upstream Compose file sets Postgres `shm_size: 128mb`. This package
omits that setting because the published SDK validator rejects it; Postgres uses
Docker's default shared-memory size. Revisit it when the SDK supports the key.

Before upgrading to Immich v3, back up the database and confirm it uses
VectorChord. Update mobile clients before the server and review the
[v3 migration guide](https://immich.app/blog/v3-migration). Immich does not support
downgrades after an upgrade.
