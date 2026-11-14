# Security policy

## Reporting a vulnerability

Please report vulnerabilities privately, through
[GitHub's private vulnerability reporting](https://github.com/13axis/turbo-cache-server/security/advisories/new)
for this repository. Do not open a public issue.

Include what is affected (version or commit, and the mode: per-team tokens,
one shared token, or no authentication), how to reproduce it, and the impact
you see. We aim to acknowledge a report within three working days and to
agree on a disclosure date with you once a fix is ready.

If the issue also affects
[brunojppb/turbo-cache-server](https://github.com/brunojppb/turbo-cache-server),
we will coordinate with its maintainer.

## Supported versions

Security fixes go into the latest release. Use the newest `v<major>.<minor>`
image tag, or pin a digest and update it when a release is published.

## Scope

In scope: the server (authentication, team isolation, the artifact routes and
storage keys), the images and binaries released here, and the GitHub Action.

Out of scope: running without authentication on a network others can reach,
weak tokens (see "Security notes" in the README), and the security of your
S3-compatible storage itself.
