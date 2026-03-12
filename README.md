# Plezy AUR Automation

This repository contains GitHub Actions workflows to automatically update the [plezy-bin](https://aur.archlinux.org/packages/plezy-bin) AUR package when upstream releases a new version.

## How it works

The workflow runs every hour and:

1. Checks the latest release version from [edde746/plezy](https://github.com/edde746/plezy)
2. Compares it with the current version in the AUR package
3. If different:
   - Downloads the new release
   - Calculates the SHA256 checksum
   - Updates `PKGBUILD` and `.SRCINFO`
   - Pushes the update to AUR
4. Creates a GitHub issue if the update fails

## Setup

1. Fork this repository to your GitHub account
2. Add the following secrets in Settings → Secrets and variables → Actions:
   - `AUR_SSH_PRIVATE_KEY`: Your SSH private key for AUR access

## Manual trigger

You can manually trigger the workflow from the Actions tab.
