[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=1231190529)

> **This repository is automatically synced from [elabit/robotmk-starter](https://github.com/elabit/robotmk-starter/tree/main/examples/cryptolibrary-simple).**
> Do not edit files here directly — changes will be overwritten on the next sync.
> Last sync: [`9b85cf3`](https://github.com/elabit/robotmk-starter/commit/9b85cf3f1a071c0c30c1a7221f8c6dcb27c78842)

---
# cryptolibrary-simple

Minimal example for using [robotframework-crypto](https://github.com/Snooz82/robotframework-crypto) with Robotmk.
Demonstrates how to store an encrypted secret in a Robot Framework suite and decrypt it at runtime using a private key file — no plaintext passwords anywhere in the codebase.

## What This Demonstrates

- Encrypting a password with `CryptoLibrary` and storing the `crypt:…` value in the suite
- Passing the key password via an environment variable (`RMKCRYPTPW`)
- Loading the private key from a file path relative to the suite

## Test Cases

| Test Case | Description |
|---|---|
| `Test Password Equality` | Decrypts an encrypted password string and asserts it equals the known plaintext |

## Key Files

| File | Purpose |
|---|---|
| `suite.robot` | Single test suite with the `Test Password Equality` test case |
| `conda.yaml` | Python environment (Python `3.12`, robotframework-crypto `0.3`) |
| `robot.toml` | Sets the `RMKCRYPTPW` environment variable consumed by CryptoLibrary |
| `keys/private_key.json` | Demo private key for decryption — replace with your own in production |
| `.devcontainer/devcontainer.json` | VS Code devcontainer with RCC pre-installed |

## Links

- [robotframework-crypto](https://github.com/Snooz82/robotframework-crypto)
- [Robot Framework](https://robotframework.org)
- [Robotmk Homepage](https://robotmk.org)


## Prerequisites

**RCC**  to create isolated self contained environments. Download from the [Robotmk release page](https://github.com/elabit/robotmk/releases/download/v4.0.0/) or use the provided script (`_dev/scripts/download-rcc.sh` / `download-rcc.ps1`).
  
## Libraries & Versions

| Library | Version |
|---|---|
| Python | `3.12` |
| Robot Framework | `7.4` |
| robotframework-crypto | `0.3` |



## How to Run

### On the console

Run directly with RCC (creates the isolated environment on first run):

```bash
rcc task script --robot robot.yaml -- robot suite.robot
```

### In VS Code / Locally

Create and activate the environment, then open VS Code from the activated environment: 

```bash
rcc task shell
code . 
```

Install the [RobtoCode](https://marketplace.visualstudio.com/items?itemName=d-biehl.robotcode) extension for VS Code to run the robot with the integrated run/debug tools.  
**This is the recommended way for the implementation of Robot Framework suites.**

### In VS Code / Devcontainer

Just press the button below. RCC is pre-installed, will create the environment and activate it for VS Code. 

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=1231190529)
