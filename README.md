# NYC Mesh VPN Action

A GitHub Action to establish a WireGuard VPN tunnel to NYC Mesh infrastructure based on provided configuration.

## Features

- Automatically configures WireGuard VPN connection
- Supports multiple server preferences with fallback
- Tests connection with configurable ping target
- Handles IP address calculations and network configuration

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `config-name` | Name of the VPN configuration to use | Yes | - |
| `private-key` | WireGuard private key for authentication | Yes | - |
| `server-preference` | Comma-separated list of server preferences (3,10,11) | Yes | `3,10,11` |
| `test-ip` | IP address to ping to test tunnel connectivity | Yes | `10.10.10.10` |

## Usage

```yaml
steps:
  - name: Setup NYC Mesh VPN
    uses: nycmeshnet/nycmesh-vpn-action@main
    with:
      config-name: "your-config-name"
      private-key: ${{ secrets.WIREGUARD_PRIVATE_KEY }}
      server-preference: "3,10,11"
      test-ip: "10.10.10.10"
```
