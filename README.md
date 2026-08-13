# Paseo Relay Image

Builds the upstream [Paseo relay](https://github.com/getpaseo/paseo-relay) and publishes it to GitHub Container Registry.

## Image

```text
ghcr.io/mtaku3/paseo-relay:7e52c8c7c96f1b8049c39acb5208012c57eb0af0
```

The tag is the pinned upstream Git commit. No mutable `latest` tag is published.

## Building

The [GitHub Actions workflow](.github/workflows/build.yml) builds the upstream Dockerfile for `linux/amd64`, publishes the image, and generates provenance and an SBOM.

The workflow runs when its configuration changes on `main` and can also be started manually from the Actions tab.

## Updating

To publish a newer relay version:

1. Update `PASEO_RELAY_REF` in `.github/workflows/build.yml` to the desired upstream commit.
2. Commit and push the change to `main`.
3. Update consumers to use the corresponding immutable image tag.
