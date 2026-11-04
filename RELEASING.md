# Publishing a Windows release

The public download repository publishes builds from the private `Mesrine67/fxmp-tools` source repository. The release workflow runs only by manual dispatch from `main` on an ephemeral GitHub-hosted Windows runner.

## One-time setup

Create the `windows-release` Actions environment and restrict deployments to the `main` branch. Add these environment secrets without copying their values into workflow files or chat:

- `FXMP_SOURCE_READ_TOKEN`: fine-grained token with `Contents: read` on `Mesrine67/fxmp-tools` only.
- `TAURI_SIGNING_PRIVATE_KEY`: the existing Tauri updater signing key.
- `TAURI_SIGNING_PRIVATE_KEY_PASSWORD`: only if the configured key uses a password.

The workflow uses the public repository's `GITHUB_TOKEN` for release assets. Third-party actions are SHA pinned and restricted by repository Actions settings. No pull-request event receives release secrets.

## Release process

1. Confirm the private source tag is immutable, version files and changelog agree, and source CI plus Windows GUI smoke passed for its commit.
2. On the public repository `main`, run **Actions → Windows release → Run workflow** and enter the exact source tag (for example, `v0.2.20`).
3. The workflow checks out and verifies the exact source tag commit, validates release contracts, builds MSI and NSIS, signs updater bundles, verifies manifest URLs and signatures, creates `SHA256SUMS.txt`, and publishes the draft only after asset checks pass.
4. Confirm the public release has both installers, both updater signatures, `latest.json`, and checksums. Test the updater from the previous installed version before closing the release qualification issues.

The public release repository's tag points to its own release metadata commit; the workflow log and release notes identify the exact private source commit used for the binaries.