# Seed-Vault
🔐 Seed Vault

Hide your seed phrase in plain sight.

Seed Vault is an offline, single-file HTML tool that camouflages your BIP39 seed phrase inside a grid of legitimate BIP39 words. The printed document looks completely uniform — every word is indistinguishable from every other. Only you know the coordinates.
⚠ v0.1 Beta — Community Review Stage. Use dummy/test words only until stable release.

The Problem
Every hardware wallet tells users to write their seed phrase on a piece of paper. If someone finds that paper, the wallet is gone. There are no second chances.
Plain text seed phrase storage is the weakest link in personal crypto security — and the industry has no good answer for it.
The Solution
Seed Vault generates a 30×10 grid of 300 BIP39 words per page. Your seed words are placed at coordinates only you choose. Every remaining cell is filled with random BIP39 words. There are no visual markers — no highlighting, no formatting, no indication of which words are yours.
To recover your phrase you need two things:

The printed document
Your coordinate key (page / row / column per word) — shown on screen only, never printed

Without both, the document is useless.
Security Model
Entropy against brute force
Finding 12 seed words in a 300-word grid, in the correct order:
C(300,12) × 12! ≈ 10²⁸ combinations
At 1 billion guesses per second: longer than the age of the universe.
Attack surface

No network requests — ever
No localStorage, sessionStorage, or cookies
No server, no backend, no telemetry
Seed words exist only in browser memory during the session
Closing the tab destroys all data

What this does NOT protect against

Exposure of your coordinate key
Physical observation during setup
Coercion ($5 wrench attack)
Both the document AND key being found together

Features

✅ Single HTML file — no install, no dependencies
✅ Fully offline — verify with DevTools → Network tab (zero requests)
✅ Nothing stored — no localStorage, no cookies
✅ Fully auditable — read every line before running
✅ 1922 BIP39 words embedded directly in the file
✅ Real-time word validation with autocomplete suggestions
✅ Conflict detection — duplicate coordinates flagged instantly
✅ Supports 12, 18, and 24-word seed phrases
✅ Multi-page support (1–20 pages)
✅ Print-ready A4 portrait output

How to Use

Download seed-vault.html
Disconnect from the internet (or verify Network tab shows zero requests)
Open the file in any browser
Follow the 4-step wizard:

Step 1 — Choose word count (12/18/24) and number of pages
Step 2 — Enter your seed phrase (real-time BIP39 validation)
Step 3 — Assign coordinates to each word (page, row, column)
Step 4 — Review your coordinate key on screen, then print


Write your coordinate key on a separate, secure medium
Print the document
Close the tab immediately

How to Verify It's Offline

Open the file in your browser
Press F12 to open DevTools
Go to the Network tab
Use the tool completely
Confirm: zero network requests

Community Review Checklist
This is a beta release. Please test and report:

 Word validation — try typos and non-BIP39 words
 Autocomplete — test partial word input
 Conflict detection — assign duplicate coordinates
 Print output — A4 fit, no blank pages between grids
 Network isolation — DevTools confirms zero requests
 DOM inspection — no seed words visible in page source after generation
 Console — no seed words logged
 All phrase lengths — 12, 18, 24 words
 Multiple pages — all pages generate and print correctly
 JavaScript security review — any vulnerabilities?

Reporting Issues
Found a bug, security issue, or have feedback?
→ Open a GitHub Issue
For security vulnerabilities please open a private issue or describe the class of vulnerability without full details until it can be patched.
Roadmap

 v0.2 — Stable release after community review
 Prevent seed words from appearing as decoys (optional toggle)
 AES-encrypted coordinate key export
 Multiple seed phrases per document
 Checksum validation per BIP39 standard

License
MIT — free to use, modify, and distribute. See LICENSE.
Disclaimer
This tool is provided for educational and security research purposes. It is not financial advice. Use at your own risk. Always maintain multiple secure backups of your seed phrase through different methods.

Single file · No dependencies · No network · No storage · Fully auditable
