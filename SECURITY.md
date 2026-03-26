# Security Policy

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

Use this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.

**Title**: Exposed Baidu Maps API Key in Public Repository

**Description**:
A Baidu Maps API key was found hardcoded in multiple configuration files within this repository.

**Exposed Credential**:
- API Key: `cM583ZCN1X1rm8zvpzTX0A50G1h37MFd`
- Service: Baidu Location Services
- Package Name: `com.woke.app`

**Affected Files**:
- `config.xml` (line containing com.qdc.plugins.baidu.location)
- `plugins/android.json`
- `plugins/fetch.json`
- `plugins/browser.json`

**Impact**:
If still valid, this key could be used to:
- Access Baidu Maps/Location services without authorization
- Potentially incur unexpected usage costs
- The key was found via Google dorking, making it publicly accessible

**Recommendation**:
1. Revoke this API key if still active
2. Remove the key from the repository (including git history)
3. Use environment variables or a secrets management solution for future projects

**Disclosure**:
I found this through Google dorking while researching security exposures. No unauthorized access was attempted.

