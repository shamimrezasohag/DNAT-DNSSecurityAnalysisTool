# DSAT-DNSSecurityAnalysisTool

## Description
The DNS Security Analysis Tool is a Python-based utility designed to conduct an in-depth security analysis of DNS configurations for multiple domains. It queries various DNS record types and performs specialized checks, including DNSSEC verification, open resolver detection, and reverse DNS mismatch analysis. This tool is handy for network administrators, cybersecurity professionals, and anyone interested in DNS security.

## Key Features
- **Comprehensive DNS Record Queries**: Retrieves various DNS record types such as A, AAAA, MX, TXT, NS, CNAME, SOA, SPF, DKIM, DNSKEY, DS.
- **DNSSEC Verification**: Checks for the implementation of DNSSEC, enhancing the security of DNS queries.
- **Open Resolver Detection**: Identifies potential open resolvers that might be used in DNS amplification attacks.
- **Reverse DNS Mismatch Analysis**: Examines mismatches between forward and reverse DNS records.
- **Anomaly Detection**: Basic analysis to identify potential anomalies and unusual entries in DNS records.
- **Response Code Logging**: Captures and logs DNS response codes for each query for further analysis.
- **Domain Name Validation**: whether the domain exists or not. If not, no further check will be done.
- **Empty Row filtering**: If the file contains an empty row, it will check and skip that part.
- **Global CDN and Anycast Analysis**: Latency comparison across multiple DNS providers (Google DNS, Cloudflare, Quad9, OpenDNS) from different regions for each domain

### Key Notes:
- **`check_open_resolver` Function**: This function uses the `dig` command to determine if the given domain is an open resolver. Ensure the environment where this script is run has the `dig` command available.
- **`check_dnssec` Function**: Performs DNSSEC validation for the domain using the specified nameservers.
- **`analyze_records` Function**: Placeholder for analyzing DNS records for anomalies. Specific logic can be implemented based on the requirements.
- **`Global Analysis`**: The tool performs global DNS analysis by querying DNS from multiple geographic locations (e.g., Google DNS, Cloudflare, Quad9, OpenDNS), providing insights into CDN and Anycast performance.
- **Reporting and Processing**: The script generates a report in the chosen format and processes each domain in the input file, showing progress with a `tqdm` progress bar.

This script should now provide comprehensive DNS security analysis, including open resolver checking and DNSSEC validation, among other features. Test this script in your environment to ensure it performs as expected. Please let me know if you encounter any issues or need further modifications!


## Prerequisites
- Python 3.x
- `dnspython` `pnadas` `tqdm` library

## Installation
1. Clone the repository:
```git clone https://github.com/shamimrezasohag/DSAT-DNSSecurityAnalysisTool.git```
2. Navigate to the cloned directory:
```cd DSAT-DNSSecurityAnalysisTool```
3. Install the required Python package:
```pip install dnspython pandas tqdm```

## Usage
Run the script from the command line by specifying the input file containing domain names and other optional parameters:
```python3 dns_security_analysis_tool.py domains.txt --format csv --output dns_security_report```

### Command-Line Arguments
- `domains-file`: Path to the file containing the list of domains for analysis.
- `--dns-server`: (Optional) DNS server to use for queries (default: 8.8.8.8).
- `--global-analysis`: (Optional) Enable global CDN and Anycast DNS analysis, comparing multiple DNS providers.
- `--format`: (Optional) output report format (`json`, `csv`, `html`).
- `--output`: (Optional) Name of the output file (without extension).

## Example:
To run the tool with global CDN analysis and produce an HTML report:
```python3 dns_security_analysis_tool.py --domains-file domains.txt --global-analysis --format html --output dns_security_report```

## Bug Reporting and Contributions

### Reporting Bugs
If you happen to encounter any bugs or issues with the DNS Security Analysis Tool, please report them to us for investigation. You can submit bug reports via our GitHub Issues page:

[Submit a Bug Report](https://github.com/shamimrezasohag/DSAT-DNSSecurityAnalysisTool/blob/main/.github/ISSUE_TEMPLATE/bug_report.md)

When you report a bug, please provide as much detail as possible, such as the steps to reproduce the issue, the expected outcome, and any relevant logs or screenshots.

### Contributing
I want you to know that contributions to this project are welcome. Please feel free to fork the repository, make changes, and submit a pull request.

For more details on how to contribute, please read our [CONTRIBUTING.md](CONTRIBUTING.md) file.

## Reporting Security Vulnerabilities

We take the security of our project seriously. If you find any security vulnerabilities in our tool, please make sure to report them responsibly. To report a security vulnerability, please follow the steps outlined in our [Security Policy](https://github.com/shamimrezasohag/dns-security-analysis-tool/SECURITY.md).

Your report should include details of the vulnerability, how it can be exploited, and any potential impact. Please only disclose the vulnerability publicly once we have had a chance to resolve it.

## Features added
- **Progress Bar**: Real-time visual feedback on script execution with a progress bar.
- **Input Validation**
- **Empty Row filtering**

## License
This project is licensed under the Apache License 2.0. For more details, please look at the [LICENSE](LICENSE) file.

## Contact
Please contact [Shamim](mailto:sohag.shamim@gmail.com) for any questions or feedback.


