# data-loss-prevention-scanner

Scans files and directories for sensitive data patterns: SSNs, credit
card numbers (Luhn-validated), email addresses, AWS access keys,
generic secrets, and IBANs. Matches are masked in output — only the
last few characters are shown.

This is a **personal portfolio project** exploring data-loss-prevention
scanning and security automation. It is a learning exercise, not a
production tool, and it has never been deployed at any employer. All
sample data is fictional.

## Quickstart

No dependencies to install — the standard library is all you need:

```bash
python3 run.py samples/leaky.txt
python3 run.py samples/clean.txt
python3 run.py samples/
```

Exit codes: `2` = usage error or unreadable path, `1` = at least one
high-severity match, `0` = no high-severity matches.

## Day-1 scope

- Pattern matching: SSN, credit card (with Luhn check), email, AWS
  access key, generic `key = value` secrets, IBAN.
- Recursive directory scanning; binary/unreadable files skipped.
- Masked findings output (text and JSON with `--json`).
