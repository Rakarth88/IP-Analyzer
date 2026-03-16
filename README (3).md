# IP/Domain Analyzer - Multi-API Security Analysis Tool

Security analysis tool for IPs and domains using AbuseIPDB, VirusTotal, and Shodan.

## 🚀 Features

- ✅ Intuitive graphical interface
- ✅ Support for single or batch analysis
- ✅ Integration with 3 major security APIs
- ✅ Results export
- ✅ Load targets from file
- ✅ Color-coded, well-formatted results
- ✅ Background analysis with progress bar

## 📋 Requirements

- Python 3.7 or higher
- WSL (Windows Subsystem for Linux) if on Windows
- Internet connection

## 🔧 Installation

### On WSL/Linux:

1. **Install Python and pip** (if not already installed):
```bash
sudo apt update
sudo apt install python3 python3-pip python3-tk -y
```

2. **Install Python dependencies**:
```bash
pip3 install requests
```

3. **Make the file executable**:
```bash
chmod +x ip_analyzer.py
```

## ▶️ Running the Program

### From WSL:

```bash
python3 ip_analyzer.py
```

or:

```bash
./ip_analyzer.py
```

### Note for WSL:
If you experience issues with the graphical interface in WSL, make sure you have an X server installed on Windows (such as VcXsrv or Xming) and that the DISPLAY variable is configured:

```bash
export DISPLAY=:0
```

Or add it to your `~/.bashrc`:
```bash
echo 'export DISPLAY=:0' >> ~/.bashrc
source ~/.bashrc
```

## 📖 How to Use

### 1. Entering IPs/Domains

- **Manually**: Type IPs or domains in the text box on the left (one per line)
- **From File**: Click "📁 Load from File" and select a .txt or .csv file

Examples:
```
8.8.8.8
1.1.1.1
malicious-site.com
example.com
192.168.1.1
```

### 2. API Selection

Select which APIs to use for the analysis:
- ☑️ AbuseIPDB
- ☑️ VirusTotal
- ☑️ Shodan

### 3. Running the Analysis

- **🔍 Analyze Single IP/Domain**: Analyzes only the first entry in the list
- **🔍 Analyze All**: Analyzes all entered IPs/domains

### 4. Viewing Results

Results appear in the right panel with color coding:
- 🟢 **Green**: Low risk / Safe
- 🟡 **Yellow**: Medium risk / Suspicious
- 🔴 **Red**: High risk / Malicious

### 5. Exporting

Click "💾 Export Results" to save the analysis to a text file.

## 🔍 Information Provided

### AbuseIPDB
- Abuse Confidence Score (0–100%)
- Number of reports
- Country and ISP
- Usage type
- Whitelist status

### VirusTotal
- Malware analysis (number of detections)
- Reputation
- Categories
- Full statistics (malicious, suspicious, harmless)

### Shodan
- Open ports
- Active services
- Known vulnerabilities (CVEs)
- Geolocation information
- Organization and ISP
- Hostnames

## 📝 Input File Format

The program accepts text files with IPs/domains separated by newlines:

```
8.8.8.8
google.com
1.1.1.1
facebook.com
185.220.101.1
```

## 🔐 Security Notes

- API keys are already embedded in the code
- All requests use HTTPS
- Results may be sensitive — handle with care
- Do not share results containing sensitive information

## ⚠️ Limitations

- **Rate Limiting**: APIs have request limits
  - AbuseIPDB: ~1,000 requests/day (free plan)
  - VirusTotal: ~500 requests/day (free plan)
  - Shodan: ~100 requests/month (free plan)
- Shodan only works with IP addresses, not domains
- VirusTotal may not have information on recently registered IPs/domains

## 🐛 Troubleshooting

### Error "ModuleNotFoundError: No module named 'tkinter'"
```bash
sudo apt install python3-tk
```

### Error "Can't connect to display"
Install and configure an X server (VcXsrv/Xming) and set:
```bash
export DISPLAY=:0
```

### API Error (401, 403)
- Verify that the API keys are correct
- Check that you have not exceeded the request limits
- Verify your internet connection

### Timeout
- Some IPs may take longer to respond
- Increase the timeout in the function or try again

## 📧 Support

For issues or questions, verify that:
1. Dependencies are correctly installed
2. API keys are valid
3. Internet connection is active
4. You have not exceeded the API limits

## 📄 License

This tool is provided "as is" for educational and security research purposes.

## 🔄 Version

**v1.0.0** - Initial release

---

**Happy Analyzing! 🔍🛡️**
