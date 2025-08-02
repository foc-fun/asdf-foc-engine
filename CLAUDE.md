# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

asdf-foc-engine is an asdf plugin for managing installations of the foc-engine tool. The foc-engine is a Starknet blockchain application engine written in Go.

## Key Commands

**Linting and Formatting:**
```bash
# Run linting (shellcheck + shfmt diff check)
./scripts/lint.bash

# Format code (shfmt write)
./scripts/format.bash
```

**Testing:**
```bash
# Test plugin locally
asdf plugin test foc-engine https://github.com/foc-fun/asdf-foc-engine.git "foc-engine --version"

# Run GitHub Actions locally (requires act)
act -j test
```

## Architecture

### Core Plugin Structure
- `bin/download` - Downloads foc-engine release artifacts from GitHub
- `bin/install` - Installs downloaded version to asdf's install directory
- `bin/list-all` - Lists all available foc-engine versions from GitHub releases
- `bin/latest-stable` - Returns the latest stable version
- `lib/utils.bash` - Shared utilities for GitHub API, version management, and error handling

### Key Functions in lib/utils.bash
- `list_github_tags()` - Fetches available versions from GitHub API
- `list_all_versions()` - Sorts and formats version list
- `download_release()` - Handles downloading and extracting releases
- `install_version()` - Manages the installation process

## Development Guidelines

### Code Style
- Use tabs for indentation in bash scripts
- All scripts must pass shellcheck and shfmt validation
- Include `set -euo pipefail` in all bash scripts
- Source `lib/utils.bash` for common functionality

### Version Handling
- Versions are fetched from GitHub releases API
- Downloads source code archives, not pre-built binaries
- Supports standard asdf version syntax (latest, specific versions)

### Error Handling
- Always use the fail() function from utils.bash for errors
- Clean up temporary files on failure using trap
- Provide clear error messages to users

### Testing Changes
1. Run linting: `./scripts/lint.bash`
2. Format code: `./scripts/format.bash`
3. Test locally: `asdf plugin test foc-engine . "foc-engine --version"`
4. Ensure GitHub Actions pass before merging

## Important Notes

- The plugin downloads source code and expects foc-engine to be built from source
- Requires docker and docker-compose for foc-engine runtime
- GitHub API rate limits may affect listing versions (60/hour unauthenticated)
- Main branch is `main`, not `master`
- Uses semantic versioning and conventional commits