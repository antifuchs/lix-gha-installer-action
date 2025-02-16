# Lix GHA Installer Action

> _Simple and opinionated action to install Lix. Strictly follows the default semantics of a Lix install._

---

### TLDR

It mostly just runs [the Lix Installer](https://lix.systems/install/#new-installs)<sup>1</sup>.

Some differences:

- We use the `channel:` ref to Nixpkgs instead of the `flake:` ref, as the `flake:` ref may have issues within the GHA ecosystem, regarding rate-limiting.
- We configure the current user as a trusted user.

### Options

#### `extra_nix_config`

A string that gets appended as-is to /etc/nix/nix.conf

#### `github_access_token`

An access token that's configured as an extra-access-tokens entry for `github.com`. If unset, the action's default access token (from `github.token`) is configured.

---

<sup>1</sup>: And checks Nix is available, and also wraps with error reporting...
