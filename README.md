# THE ANCIENT AGE - launcher updates

Official distribution point for **THE ANCIENT AGE Balance Patch** and **THE ANCIENT AGE Launcher**
(a small balance patch for Age of the Ring 9.3.3).

This repository only contains release information and signed release files. It does not contain the
source code of THE ANCIENT AGE, and it never contains Age of the Ring files: the patch is built on each
player's PC from their own Age of the Ring installation, which is never modified.

## For players

- **First installation:** download the ZIP of the latest Balance Patch release, extract it and run the
  Setup. The README inside the ZIP explains everything.
- **Updates:** launchers that support online updates check this repository when they start (you can
  turn this off in SETTINGS). When a new version is available, the UPDATES tab shows it, and nothing is
  downloaded or installed until you press **UPDATE NOW**. You can always keep playing your installed
  version, also without internet.
- **Beta:** beta versions are only offered if you turn on "Beta updates" in SETTINGS.

## How releases are protected

- Every release file is listed with its SHA-256 and size in a channel manifest (`channels/`), and every
  manifest is signed with the project's minisign key (`keys/`). The launcher refuses anything that is not
  signed with that key, that is older than what it already accepted, or that comes from another address.
- See [SECURITY.md](SECURITY.md) to verify a download by hand.

## Layout

```
channels/stable.json(.minisig)   stable channel manifest (signed)
channels/beta.json(.minisig)     beta channel manifest (signed)
keys/                            public keys used to verify the signatures
Releases                         patch-X.Y.Z and launcher-X.Y.Z (files never change after publication)
```
