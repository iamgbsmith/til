# Understanding CVSS Scores

__Category: Security__

The Common Vulnerability Scoring System (CVSS) is an industry standard for assessing the severity of software security vulnerabilities. 

When vulnerabilities are found, they are rated with a score from 0.0 to 10.0, with 10.0 being the most severe. Security and penetration testing reports typically include CVSS scores for issues found during testing.

Version V3.1 of CVSS scores released in June 2019 provides the following guidance:

| Severity     | Base Score Range    |
| ------------ |-------------------- |
| None         | 0.0                 |
| Low          | 0.1 to 3.9          |
| Medium       | 4.0 to 6.9          |
| High         | 7.0 to 8.9          |
| Critical     | 9.0 to 10.0         |

Critical and High vulnerabilities should be immediately addressed. Medium vulnerabilities should be priorised for remediation. Low (sometimes known as Observational) vulnerabilities will need to be assessed against organisational risk management frameworks to determine remediation priorities. Depending on risk profiles and risk management, Low severity vulnerabilities may not require any remediation.

CVSS scores can be calculated using https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator although they are normally determined when published to the searchable CVE database at https://cve.mitre.org/
