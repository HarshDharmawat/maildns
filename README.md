# maildns
A simple Go CLI tool to verify email domain DNS configuration (MX, SPF, and DMARC)

## Features

- Checks for MX records
- Detects SPF records (`v=spf1`)
- Detects DMARC records (`v=DMARC1`)
- Reads domains from standard input (stdin)
- Outputs clean, CSV-style results

## Output Format
domain, hasMX, hasSPF, spfRecord, hasDMARC, dmarcRecord

## Example output:
example.com, true, true, v=spf1 include:_spf.google.com ~all, true, v=DMARC1; p=none;

## Requirements
Go 1.18 or newer
Network access for DNS lookups

## Notes
Only the first SPF or DMARC record found is returned
Domains without records will show false and empty fields
DNS lookup errors are handled silently to keep output clean

## Use Cases
Email deliverability audits
Domain hygiene checks
Bulk DNS validation
Security and compliance reviews
