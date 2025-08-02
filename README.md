<div align="center">

# asdf-foc-engine [![Build](https://github.com/foc-fun/asdf-foc-engine/actions/workflows/build.yml/badge.svg)](https://github.com/foc-fun/asdf-foc-engine/actions/workflows/build.yml) [![Lint](https://github.com/foc-fun/asdf-foc-engine/actions/workflows/lint.yml/badge.svg)](https://github.com/foc-fun/asdf-foc-engine/actions/workflows/lint.yml)

[foc-engine](https://github.com/foc-fun/foc-engine) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

## About

This plugin enables you to install and manage different versions of foc-engine using the asdf version manager. The foc-engine is a Starknet blockchain application engine written in Go, designed for building and deploying applications on the Starknet blockchain.

# Contents

- [About](#about)
- [Dependencies](#dependencies)
- [Install](#install)
- [Usage](#usage)
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
asdf plugin add foc-engine https://github.com/foc-fun/asdf-foc-engine.git
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

# Usage

Once installed, you can use foc-engine to build and deploy Starknet applications:

```shell
# Check installed version
foc-engine --version

# Use foc-engine commands for your Starknet projects
# (Refer to foc-engine documentation for specific commands)
```

## Development

For plugin development:

```shell
# Run linting
./scripts/lint.bash

# Format code
./scripts/format.bash

# Test the plugin locally
asdf plugin test foc-engine . "foc-engine --version"
```

# Contributing

Contributions of any kind welcome! See the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/foc-fun/asdf-foc-engine/graphs/contributors)!

# License

See [LICENSE](LICENSE) © [Brandon Roberts](https://github.com/foc-fun/)
