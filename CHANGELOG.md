# Changelog

All notable changes to this fork are listed here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and releases follow
[Semantic Versioning](https://semver.org/).

This fork continues the version line of
[brunojppb/turbo-cache-server](https://github.com/brunojppb/turbo-cache-server):
each release names the upstream version it is based on. Its tags start with
`v` (`v5.1.0`), upstream's do not (`5.0.4`). Changes made upstream are in
[upstream's releases](https://github.com/brunojppb/turbo-cache-server/releases).

## [Unreleased]

## [5.1.0]

Based on upstream 5.0.4.

### Added

- Multi-tenancy: per-team tokens. `TURBO_TOKENS_DIR` names a directory with
  one file per team (the file name is the team, the content the SHA-256 hex
  of its token). A request must carry the token of the team it names: no or
  an unknown token is `401`, another team's token or no team named is `403`.
  The directory is re-read every 10 seconds, so teams are added, removed and
  rotated without a restart. See "Multi-tenancy: per-team tokens" in the
  README.
- Release images carry a CycloneDX SBOM per platform, attached to the image
  digest as an OCI 1.1 referrer, and a build provenance attestation; release
  binaries have provenance attestations too.
- Images are also tagged `<major>.<minor>`.

### Changed

- The server refuses to start when both `TURBO_TOKEN` and `TURBO_TOKENS_DIR`
  are set, or when `TURBO_TOKENS_DIR` cannot be read. With
  `TURBO_TOKENS_DIR` unset, behaviour is the same as upstream 5.0.4.
- Binaries are built with cargo-auditable, which embeds their dependency list
  for SBOM and vulnerability scanners.
- Images are published as `ghcr.io/13axis/turbo-cache-server`, and the GitHub
  Action is `13axis/turbo-cache-server@v<version>`.

[Unreleased]: https://github.com/13axis/turbo-cache-server/compare/v5.1.0...HEAD
[5.1.0]: https://github.com/13axis/turbo-cache-server/releases/tag/v5.1.0
