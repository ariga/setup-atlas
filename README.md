# setup-action

A GitHub Action for installing up [Atlas](https://github.com/ariga/atlas).

This action is used for installing Atlas on the Github runner.

> Please note that for most use cases, you should first consider using [Atlas Action](https://github.com/ariga/atlas-action) which can save you a lot of work.

### Usage

Add `.github/workflows/setup-atlas.yaml` to your repo with the following contents:

```yaml
name: My Action Name
run-name: I'm using Atlas 🚀
on: [push]
jobs:
  use-atlas:
    runs-on: ubuntu-latest
    steps:
      - uses: ariga/setup-atlas@master
      - run: atlas version
```

#### version

By default, the `latest` version of Atlas is being used. If you want to lock a specific version of Atlas, you can do so by specifing the `version` parameter.

```yaml
      - uses: ariga/setup-atlas@master
        with:
            version: "vX.Y.Z"
```


### Legal

The source code for this GitHub Action is released under the Apache 2.0
License, see [LICENSE](LICENSE).

This action downloads a binary version of [Atlas](https://atlasgo.io) which
is distributed under the [Ariga EULA](https://ariga.io/legal/atlas/eula).