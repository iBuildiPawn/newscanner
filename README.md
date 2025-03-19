# 🛡️ NewScanner - Advanced Network Vulnerability Scanner

NewScanner is a high-performance network vulnerability scanner written in Rust that combines service detection, CDN bypass capabilities, and vulnerability scanning using the National Vulnerability Database (NVD).

## ✨ Features

- 🔍 **Service Detection**: Identifies running services and their versions
- 🌐 **CDN Detection & Bypass**: Detects and attempts to bypass CDN protection
- 🔒 **Vulnerability Scanning**: Checks for known vulnerabilities using NVD database
- 💾 **Local Caching**: SQLite-based caching for faster repeated scans
- 🚀 **High Performance**: Written in Rust for maximum speed and reliability
- 📝 **Detailed Reporting**: Comprehensive vulnerability reports with CVSS scores

## 🚀 Quick Start

### Prerequisites

- Rust (latest stable version)
- SQLite
- NVD API Key (get it from [NVD API Key Request](https://nvd.nist.gov/developers/request-an-api-key))

### Installation

1. Clone the repository:
```bash
git clone https://github.com/iBuildiPawn/newscanner.git
cd newscanner
```

2. Create a `.env` file:
```bash
echo "NVD_API_KEY=your_api_key_here" > .env
echo "DATABASE_URL=sqlite:./vulndb.sqlite" >> .env
```

3. Build the project:
```bash
cargo build --release
```

### Usage

Use the provided shell script for easy scanning:

```bash
# Basic scan
./scan.sh example.com

# Scan specific ports
./scan.sh -p 80,443 example.com

# Verbose output
./scan.sh -v example.com

# Show help
./scan.sh --help
```

## 📊 Example Output

```
🔍 Network Vulnerability Scanner
=================================
Target: example.com
Ports: 80,443
CDN Bypass: Enabled
Vulnerability Scanning: Enabled

Port Scan Results
================
Port 80: OPEN
  Service: nginx
  Version: 1.18.0
  Vulnerabilities Found: 2
    - CVE-2021-XXXX (CVSS: 7.5) - Critical
    - CVE-2021-YYYY (CVSS: 5.5) - Medium
```

## 🛠️ Advanced Configuration

The scanner can be configured through environment variables in the `.env` file:

```env
# Required
NVD_API_KEY=your_api_key_here
DATABASE_URL=sqlite:./vulndb.sqlite

# Optional
RUST_LOG=info  # debug, info, warn, error
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- National Vulnerability Database (NVD) for providing vulnerability data
- The Rust community for excellent networking and security crates