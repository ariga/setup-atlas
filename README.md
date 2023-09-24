# setup-action

A GitHub Action for installing [Atlas](https://github.com/ariga/atlas).

> See the docs for other [Atlas GitHub Actions](https://atlasgo.io/integrations/github-actions) for operations such as linting, syncing, or deploying your migration directory. 

## Usage

Add `.github/workflows/deploy-schema.yaml` to your repo with the following contents:

```yaml
name: Deploy schema changes
run-name: I'm using Atlas 🚀
on: [push]
jobs:
  use-atlas:
    runs-on: ubuntu-latest
    steps:
      - uses: ariga/setup-atlas@master
      - run: atlas version
      # - run: atlas schema apply ... 
```

## Inputs

### Version

By default, the `latest` version of Atlas is being used. If you want to lock a specific version of Atlas, you can do so by specifing the `version` parameter.

```yaml
      - uses: ariga/setup-atlas@master
        with:
            version: "vX.Y.Z"
```
### cloud-token

The Atlas Cloud token to use for authentication. Must be passed as a secret.
```yaml
      - uses: ariga/setup-atlas@master
        with:
            cloud-token: ${{ secrets.ATLAS_CLOUD_TOKEN }}

## Legal

The source code for this GitHub Action is released under the Apache 2.0
License, see [LICENSE](LICENSE).

This action downloads a binary version of [Atlas](https://atlasgo.io) which
is distributed under the [Ariga EULA](https://ariga.io/legal/atlas/eula).