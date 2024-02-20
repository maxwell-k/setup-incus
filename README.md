# setup-incus

A GitHub Action which installs and configures [Incus] on a default GitHub-hosted
runner. This action uses the stable Ubuntu packages from [Zabbly]. An example of
using this action in a job is below:

<!-- embedme .github/workflows/readme.yaml#L1-L12 -->

```
jobs:
  main:
    runs-on: ubuntu-latest
    steps:
      - uses: maxwell-k/setup-incus@main
      - run: |
          set -x
          incus admin init --auto
          incus --version
          incus launch images:debian/12/cloud c1
          incus exec c1 -- cloud-init status --wait
          incus exec c1 -- cat /etc/os-release
```

[Zabbly]: https://github.com/zabbly/incus
[Incus]: https://github.com/lxc/incus

<!--
README.md
Copyright 2024 Keith Maxwell
SPDX-License-Identifier: CC0-1.0
-->

<!-- vim: set filetype=markdown.embedme.htmlCommentNoSpell : -->
