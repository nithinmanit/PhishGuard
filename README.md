# PhishGuard 

A Python tool that analyzes URLs and detects phishing attempts using 
rule-based analysis and a machine learning classifier.

## What it does
- Analyzes a URL against 10+ suspicious pattern rules
- Runs it through an ML model trained on 549,000 real URLs
- Produces a risk score, verdict, and visual breakdown chart

## How it works
**Layer 1 — Rules:** Checks for HTTP, IP addresses, suspicious words,
bad TLDs, brand spoofing, excessive hyphens/dots, and more.

**Layer 2 — ML:** A Random Forest classifier trained on 549k URLs
with 83% accuracy. Uses class balancing to prioritize catching
phishing over avoiding false alarms.

**Combined verdict:** SAFE / SUSPICIOUS / DANGEROUS

## How to run
```bash
pip install scikit-learn pandas matplotlib joblib
python PhishGuard.py
```

## Example output
```
PhishGuard Analysis — http://paypa1.xyz/login/verify
──────────────────────────────────────────────────
  +15   Uses HTTP instead of HTTPS
  +10   Suspicious words found: login, verify
  +10   Suspicious TLD
  +40   ML model flagged this as phishing (100% confidence)
──────────────────────────────────────────────────
  Score : 75
  Result: 🚨 DANGEROUS
```

## What I learned
- URL parsing with `urllib`
- Pattern matching with `re` (regex)
- Data handling with `pandas`
- Machine learning with `sklearn` (Random Forest, train/test split,
  precision/recall tradeoffs)
- Data visualization with `matplotlib`
- Version control with Git and GitHub

## Limitations
URL-only analysis has limits. A convincing domain on a clean-looking
URL can evade detection without inspecting actual page content —
a known limitation of static analysis.

## Built by
Nithin — First year CSE, 2026
