# BackerStreetScan Data Flow

This document describes the data flow within the BackerStreetScan project, focusing on how information is processed from user input to scan results.

## User Input

The data flow begins when a user interacts with the BackerStreetScan command-line interface. The primary input from the user includes:

- Target IP address or hostname.
- Ports or port ranges to scan.
- Selection of a scanning technique.

## User Interface

BackerStreetScan uses the Rich library to create a visually appealing command-line interface for user interaction. The interface displays input prompts, scan results, and progress information.

## Port Scanning Modules

### 1. TCP SYN Scan

- User selects TCP SYN Scan.
- The TCP SYN Scan module receives user input.
- Custom TCP SYN packets are constructed for each specified port.
- Packets are sent to the target IP address.
- Responses are captured and analyzed.
- Scan results (open or closed ports) are displayed to the user.

### 2. TCP Connect Scan

- User selects TCP Connect Scan.
- The TCP Connect Scan module receives user input.
- Connection attempts are made to each specified port.
- Port states (open, closed, or filtered) are determined based on responses.
- Scan results are displayed.

### 3. FIN Scan, XMAS Scan, NULL Scan, ACK Scan

- Similar data flow to TCP SYN Scan, with variations in packet construction and analysis depending on the scan type.

### 4. Window Scan

- User selects Window Scan.
- The Window Scan module receives user input.
- Custom TCP SYN packets are constructed.
- Packets are sent to the target IP address.
- Responses are captured and analyzed to determine the window size.
- Scan results are displayed.

### 5. UDP Scan

- User selects UDP Scan.
- The UDP Scan module receives user input.
- Custom UDP packets are constructed for each specified port.
- Packets are sent to the target IP address.
- Responses are captured and analyzed.
- Scan results (open or closed UDP ports) are displayed to the user.

## Display Results

Scan results, including open and closed ports, are presented to the user in a visually appealing format using the Rich library. Open ports are highlighted in green, closed ports in red, and other relevant information is displayed.

## Conclusion

BackerStreetScan follows a structured data flow, starting from user input, passing through scanning modules, and concluding with the presentation of scan results in an interactive and informative manner. This data flow ensures that users can easily initiate scans, interpret results, and make informed decisions regarding network security.
