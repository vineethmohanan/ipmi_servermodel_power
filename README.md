# ipmi_servermodel_power

Collect server model, power draw, and hardware inventory from one or many BMCs over IPMI,
without logging into each machine.

## Why
During server and storage validation I needed a quick way to confirm the model, firmware,
and power consumption of every node in a test rack. This script automates that with ipmitool.

## Features
- Reads server model / FRU details
- Reports current, min, max and average power (DCMI)
- Lists sensors (temperature, fans, PSUs) and their status
- Works on any BMC that supports IPMI 2.0 (iDRAC, iLO, XCC, generic BMCs)

## Requirements
- Linux with `ipmitool` installed (see [docs/setup-ubuntu.md](docs/setup-ubuntu.md))
- Network access to the BMC and its credentials

## Usage
    ./ipmi_script.sh <bmc-ip> <username> <password>

## Example output
See [examples/sample-output.txt](examples/sample-output.txt).

## Command reference
Common ipmitool commands: [docs/ipmi-command-reference.md](docs/ipmi-command-reference.md)

## Roadmap
- [ ] Read credentials from env vars instead of arguments
- [ ] Multi-host input file and CSV/JSON output
- [ ] Redfish support
- [ ] AI-agent interface: see ipmi-mcp-server

## License
MIT
