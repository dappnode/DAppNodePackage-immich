# DAppNodePackage-immich
Dappnode Immich package - Self-hosted photo and video management solution

Requires Dappnode Core 0.3.19 or newer for the Postgres shared-memory setting
(supported since Dappmanager 0.2.120).

The shared upstream-bump workflow tracks `immich-app/immich` and updates both
Immich services through `IMMICH_VERSION`. Review each proposed update against
the matching upstream release notes and Compose file before merging. Valkey and
Postgres remain pinned in `docker-compose.yml` and must be reviewed alongside
Immich updates; do not automatically upgrade the Postgres major version against
an existing data volume.

Before upgrading to Immich v3, back up the database and confirm it uses
VectorChord. Update mobile clients before the server and review the
[v3 migration guide](https://immich.app/blog/v3-migration). Immich does not support
downgrades after an upgrade.
