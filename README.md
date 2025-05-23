# Netbird Connect GitHub Action

## Description

This GitHub Action allows you to connect your workflow to your Netbird network. You can use it to set up a Netbird peer and connect it to your Netbird network.

## Inputs

| Input       | Description                                                                                                               | Required | Default Value |
|-------------|---------------------------------------------------------------------------------------------------------------------------|----------|---------------|
| `setup-key` | Setup key obtained from the Management Service Dashboard (used to register the peer).                                     | Yes      | N/A           |
| `hostname`  | Sets a custom hostname that is visible from the Netbird Dashboard. If not provided, a default hostname will be generated. | No       | ' '           |
| `args`      | Optional additional arguments to pass to the `netbird up` command.                                                        | No       | ' '           |

## Example Usage

```yaml
name: Connect to Netbird
on:
  push:
    branches:
      - main

jobs:
  netbird:
    name: Connect to Netbird
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Netbird Connect
        id: netbird
        uses: Lupise/netbird-connect@1
        with:
          setup-key: ${{ secrets.GH_RUNNERS_NETBIRD_SETUP_KEY }}
```
