# VoidB SSH Plugin (`voidb-plugin-ssh`)

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Independent process plugin for [VoidB](https://github.com/limmytian/voidb) for SSH terminal sessions, port forwarding, and SFTP remote management.

## Features

- **Autonomous Process Architecture**: Runs in an isolated OS process communicating with VoidB via `stdio-jsonrpc`.
- **Tri-Modal Operation**:
  - `test`: Automated connectivity and host key verification.
  - `tui`: Standalone full-screen interactive terminal interface.
  - `serve`: `stdio-jsonrpc` protocol server for AI Agents and automated orchestration.
  - Domain commands: Command execution, SFTP file transfer, port forwarding.

## Usage & Operational Modes

```bash
# Connectivity test
voidb-cli ssh test --profile prod-server

# Launch standalone interactive fullscreen SSH terminal
voidb-cli ssh tui --profile prod-server

# Machine / Agent stdio-jsonrpc server
voidb-cli ssh serve
```

## Optional local SDK development

Release and CI builds resolve SDK/core from the immutable Git revision in Cargo.toml. To test against a sibling `../voidb` checkout, explicitly opt in with `cargo --config .cargo/config.local.example.toml test --all-targets`. Do not commit an active `.cargo/config.toml` path override.
