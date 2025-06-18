<div align="center">

# asdf-foc-engine [![Build](https://github.com/b-j-roberts/asdf-foc-engine/actions/workflows/build.yml/badge.svg)](https://github.com/b-j-roberts/asdf-foc-engine/actions/workflows/build.yml) [![Lint](https://github.com/b-j-roberts/asdf-foc-engine/actions/workflows/lint.yml/badge.svg)](https://github.com/b-j-roberts/asdf-foc-engine/actions/workflows/lint.yml)

[foc-engine](https://github.com/b-j-roberts/foc-engine) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

# Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Contributing](#contributing)
- [License](#license)

# Dependencies

- `bash`, `curl`, `tar`, and [POSIX utilities](https://pubs.opengroup.org/onlinepubs/9699919799/idx/utilities.html).
- `docker` and `docker compose` [setup](https://docs.docker.com/compose/install/).
- `jq` and `yq`.

# Install

Plugin:

```shell
asdf plugin add foc-engine
# or
asdf plugin add foc-engine https://github.com/b-j-roberts/asdf-foc-engine.git
```

foc-engine:

```shell
# Show all installable versions
asdf list-all foc-engine

# Install specific version
asdf install foc-engine latest

# Set a version globally (on your ~/.tool-versions file)
asdf global foc-engine latest

# Now foc-engine commands are available
foc-engine --version
```

Check [asdf](https://github.com/asdf-vm/asdf) readme for more instructions on how to
install & manage versions.

# Contributing

Contributions of any kind welcome! See the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/b-j-roberts/asdf-foc-engine/graphs/contributors)!

# License

See [LICENSE](LICENSE) © [Brandon Roberts](https://github.com/b-j-roberts/)
