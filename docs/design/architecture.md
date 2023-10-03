# BackerStreetScan Architecture

## Overview

BackerStreetScan is a Python-based network scanning tool that allows users to perform various port scanning techniques on a target host. It utilizes the Scapy library for network packet crafting and sniffing. This document provides an overview of the architecture of BackerStreetScan.

## Components

### 1. User Interface

The user interface is handled through the command line using the Rich library. It provides an interactive and visually appealing interface for users to input target IP addresses, ports, and select scan types.

### 2. Port Scanning Modules

BackerStreetScan supports multiple port scanning techniques, each implemented as a separate function:

- **TCP SYN Scan**: Scans for open TCP ports by sending TCP SYN packets and analyzing responses.
- **TCP Connect Scan**: Connects to ports using TCP and determines their state.
- **FIN Scan**: Scans for open ports by sending TCP FIN packets.
- **XMAS Scan**: Scans for open ports by sending TCP packets with various flags set.
- **NULL Scan**: Scans for open ports by sending TCP packets with no flags set.
- **ACK Scan**: Scans for open ports by sending TCP ACK packets and analyzing responses.
- **Window Scan**: Scans for open ports by analyzing TCP window size.
- **UDP Scan**: Scans for open UDP ports by sending UDP packets and analyzing responses.

Each scanning module communicates with the target host and interprets the responses to determine the state of the ports.

### 3. Scapy Library

Scapy is used for crafting and sending network packets. It allows BackerStreetScan to construct custom packets for various scanning techniques and capture responses for analysis.

## Execution Flow

1. User provides the target IP address and a list of ports or port ranges to scan.
2. The user selects one of the available scanning techniques.
3. BackerStreetScan invokes the corresponding scanning module.
4. The scanning module constructs and sends packets to the target host.
5. Responses from the target host are captured and analyzed.
6. The scan results (open or closed ports) are displayed to the user in the console.

## Dependencies

- Scapy: Used for network packet manipulation.
- Rich: Used for creating a visually appealing command line interface.

## Future Enhancements

The architecture can be extended to support additional scanning techniques, improve user interaction, and enhance the reporting of scan results.

## Conclusion

BackerStreetScan provides a modular and extensible architecture for conducting network scans using various scanning techniques. It offers an interactive and user-friendly experience for network administrators and security professionals.
