# IoT Network Scanner and Dashboard

A comprehensive solution for monitoring, securing, and managing IoT devices on your network.

## Quick Start

To run the IoT Network Scanner:

1. Run the batch file:
   ```
   IoT_Network_Scanner.bat
   ```

2. Select an option from the menu:
   - Option 1: Start Web Dashboard
   - Option 2: Run Network Scan
   - Option 3: Run Advanced Network Scan
   - Option 4: Run Scanner with Telegram Integration

3. For the Web Dashboard, open your browser and navigate to:
   ```
   http://localhost:5000
   ```

## Scanning Options

### Network Range
- You can specify a custom network range for scanning (e.g., 192.168.1.0/24)
- Leave blank to use the default network range (your local subnet)
- For faster scans, use a smaller range (e.g., 192.168.1.1-20)

### Scan Types
- **Fast Scan**: Very quick scan that checks only the most common ports
  * Significantly faster (completes in seconds)
  * Limited information but good for a quick network overview
  * Best for large networks or when you need results quickly

- **Normal Scan**: Standard scan with balanced speed and thoroughness
  * Moderate speed (completes in minutes)
  * Checks common ports and services
  * Good for routine network monitoring

- **Deep Scan**: Comprehensive but slower scan that includes:
  * OS detection
  * Service version detection
  * Extensive port scanning
  * Device fingerprinting
  * Can take 10+ minutes depending on network size

### Optimizing Scan Performance
- Use Fast Scan option when you need quick results
- Specify a smaller network range to reduce scan time
- For the web dashboard, use Fast Scan to avoid timeouts
- Schedule deep scans during off-hours
- Consider scanning specific devices rather than the entire network

### Scan Progress
- The scanner displays real-time progress during scanning
- Progress indicator shows percentage completed
- "Scanning network... X%" will update as the scan progresses

## System Requirements

- Python 3.7 or compatible version
- Windows, macOS, or Linux operating system
- Network access for device scanning

## Package Compatibility

The application requires specific package versions to work with Python 3.7:

- protobuf==3.20.3
- python-engineio==4.3.4
- python-socketio==5.1.0
- flask-socketio==5.1.1
- flask==2.0.3
- requests==2.27.1
- pandas==1.3.5
- numpy==1.21.6
- scikit-learn==1.0.2
- matplotlib==3.5.3
- eventlet==0.30.2
- python-dotenv==0.21.0
- python-nmap==0.7.1
- scapy==2.4.5
- netifaces==0.11.0

## Project Structure

```
iot/
├── README.md                      # Main project documentation
├── IoT_Network_Scanner.bat        # All-in-one batch file for the application
├── config/                        # Configuration directory
│   └── config.json                # Main configuration file
├── data/                          # Data storage directory
│   ├── device_history.json        # Device history data
│   ├── known_devices.json         # Known devices database
│   └── scan_results_*.json/txt    # Scan result files
├── reports/                       # Report directory
│   └── scan_report_*.html         # HTML scan reports
├── web_dashboard/                 # Web dashboard component
│   ├── run.py                     # Main entry point
│   ├── app.py                     # Flask application
│   ├── network_scanner.py         # Network scanning functionality
│   ├── mac_tracker.py             # Device tracking
│   ├── db_handler.py              # Database handling
│   ├── threat_analysis.py         # Threat analysis
│   ├── static/                    # Static files
│   │   ├── css/                   # CSS stylesheets
│   │   │   └── style.css          # Main stylesheet
│   │   └── js/                    # JavaScript files
│   │       ├── dashboard.js       # Dashboard functionality
│   │       └── devices.js         # Device management
│   └── templates/                 # HTML templates
│       ├── index.html             # Main dashboard page
│       └── devices.html           # Device management page
├── simple_scan.py                 # Simple network scanning script
├── advanced_network_scanner.py    # Advanced network scanning script
└── scanner_with_telegram.py       # Scanner with Telegram integration
```

## Features

### Web Dashboard
- Real-time device monitoring
- Device statistics and visualization
- Security alerts for unauthorized devices
- Network scanning and device management
- Threat detection and analysis

### Network Scanner
- Basic network scanning
- Advanced scanning with port detection
- Device tracking by MAC address
- Unauthorized device detection
- Custom network range specification
- Deep scan option for thorough analysis

### Telegram Integration
- Receive alerts via Telegram
- Control the scanner remotely
- Get scan reports and notifications

## Troubleshooting

If you encounter issues:

1. Make sure you're using Python 3.7
2. Check that all required directories exist
3. Verify that all packages installed correctly
4. Try running the Python scripts directly:
   ```
   cd web_dashboard
   python run.py
   ```

## License

This project is licensed under the MIT License - see the LICENSE file for details.