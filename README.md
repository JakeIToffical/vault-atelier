# Vault Atelier — Ledger Backup Studio

[**Open the web app**](https://jakeitoffical.github.io/vault-atelier/Ledger-Backup-Studio.html) · [Download the HTML file](https://github.com/JakeIToffical/vault-atelier/raw/refs/heads/master/Ledger-Backup-Studio.html)

An independent, single-file browser client for editing Ledger Passwords nickname backups. Maintained by [JakeIToffical](https://github.com/JakeIToffical). Not affiliated with or endorsed by Ledger.

This project develops only the browser client. Its current file tree contains no Ledger firmware, firmware build files or firmware tests. The repository currently retains its fork relationship and upstream Git history.

## Features

- Open an existing JSON backup or back up your Ledger over USB.
- Add nicknames in bulk or remove entries from the draft.
- Sort the full list alphabetically or move individual entries.
- Download the edited backup as a new file.
- Restore a checked draft, with a separate safety backup and on-device confirmation.
- Choose English, German, French or Spanish in the app.

The app keeps retained entries and their derivation parameters unchanged. It updates `parsed` and `raw_metadatas` consistently. Actual passwords are generated only by your Ledger. Never enter a recovery phrase or private keys.

## Open and self-host

Use the [hosted app](https://jakeitoffical.github.io/vault-atelier/Ledger-Backup-Studio.html), or download `Ledger-Backup-Studio.html` and open it in Chrome or Edge. The entire application is in that one file, with no installation or external libraries required.

For USB operations, connect and unlock your Ledger, open the Passwords app, and close Ledger Live and other Ledger tabs. WebUSB requires Chrome/Edge and a secure context. If USB is unavailable when opening the downloaded file directly, serve it over your own HTTPS hosting or start a local server in this folder:

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

Then open `http://localhost:8765/Ledger-Backup-Studio.html`.

Host only the app, never your personal backup files. Backup contents are processed locally in your browser and are not uploaded by the app. The language preference is stored locally when the browser permits it.

## Restore and safety

**Use at your own risk.** This independent tool is provided without warranty. Errors or interrupted restores may cause data loss or make passwords inaccessible.

Restoring replaces the entire nickname list on the device. Before every restore, keep a separate, unchanged backup, review the full target list, and confirm the operation on your Ledger. Check the result on the device afterwards. A complete hardware backup/restore cycle has not been verified.

## Compatibility

The backup format and USB protocol were checked against LedgerHQ/app-passwords commit `bf2319b8ed8abcb9c77173945d27c33d7927155b`. App information was successfully read from a Nano X running Passwords 1.4.1. Supported entry generation versions are 0 and 1.

Limits include 178 entries, printable ASCII nicknames of 1–19 bytes, and up to 4096 bytes of metadata. Generation 1 supports password lengths up to 64 characters; 4- and 6-digit PIN entries require numbers only. Unknown generation versions, corrupt backups and inconsistent representations are rejected.

Compatibility with current Ledger Passwords releases is the goal, not a guarantee for future versions. Each new Ledger release needs a format, protocol and restore compatibility check. If these interfaces remain unchanged, the client will generally need no changes.

## License and attribution

Distributed under the [Apache License 2.0](LICENSE). Upstream sources and adaptations are documented in [NOTICE](NOTICE) and [THIRD-PARTY.md](THIRD-PARTY.md). The license does not grant general rights to Ledger trademarks.

No personal backups or development test artifacts are included in the current repository tree.
