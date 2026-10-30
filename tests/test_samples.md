# Test Results

Python version used: 3.__ | Operating system: ________ | Date: ________

| # | Input | Expected result | Actual result | Pass/Fail |
|---|-------|-----------------|---------------|-----------|
| 1 | https://www.example.com/login | No listed warning signs | No listed warning signs found. This does NOT prove safety. | PASS |
| 2 | http://192.0.2.10/account | IP address + HTTP | Uses an IP address instead of a familiar domain. Uses HTTP. HTTPS alone does not prove trust. REVIEW CAREFULLY: 2 warning sign(s) found. | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | Contains an @ symbol; inspect carefully. Uses HTTP. HTTPS alone does not prove trust. REVIEW CAREFULLY: 2 warning sign(s) found. | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | Contains many hostname segments/subdomains. REVIEW CAREFULLY: 1 warning sign(s) found. | PASS |
| 5 | https://xn--example.invalid/ | Punycode-style hostname | Contains a punycode-style hostname. REVIEW CAREFULLY: 1 warning sign(s) found. | PASS |

## Bonus checks

| Input | Actual result |
|-------|---------------|
| (empty, just Enter) | No URL entered. |
| www.example.com | Uses HTTP. HTTPS alone does not prove trust. |
| https://secure-login.example.invalid | No listed warning signs found. This does NOT prove safety. |
| http://[bad | This text is not a valid URL format. |

## Notes

The line "REVIEW CAREFULLY" is not in the original expected results because I added it as an improvement, so every row with a warning ends with it.
What surprised me most was https://secure-login.example.invalid. It sounds suspicious, but the checker finds nothing, which shows that "no warning signs" does not mean safe.
Before my fix, typing http://[bad crashed the program. Now it prints a clear message and keeps running.
