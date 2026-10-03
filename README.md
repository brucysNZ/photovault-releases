# PhotoVault for macOS — releases

This repository holds two things and nothing else:

- **`appcast.xml`** — the update feed. PhotoVault reads it to ask whether a
  newer version exists. It is served at
  <https://brucysnz.github.io/photovault-releases/appcast.xml>.
- **the installers** — each release of PhotoVault, attached to the
  [`downloads`](https://github.com/brucysNZ/photovault-releases/releases/tag/downloads)
  release.

There is no source code here. PhotoVault itself lives in a private repository.

## Why this is public, and why that is safe

An update feed has to be readable by the application without a password, on any
network, so it is published the way every Mac application publishes one. What
makes an update trustworthy is not secrecy but the signature: every installer is
signed with PhotoVault's private key, and the application refuses any update
whose signature does not match the public key built into it. A replaced or
tampered file is rejected rather than installed. The installers are also signed
and notarised with Apple, so macOS checks them again before they run.

## Why it is not hosted at home

The feed and the installers must stay reachable even when no machine of ours is
running. They are served by GitHub's content network rather than from a computer
in the house, so a power cut, a reboot or an unplugged cable cannot break
anybody's update.
