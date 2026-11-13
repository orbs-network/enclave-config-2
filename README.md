# enclave-config-2

Public release records and the encrypted lane file of the **staging** co-signer audit pair (AWS Nitro Enclave and GCP Confidential Space) for the perps-b stack.

| Path | Holds |
|---|---|
| `lanes.enc` | the lanes the co-signers watch, AES-256-GCM encrypted; `sha256sum lanes.enc` matches `laneFile.sha256` in each co-signer's `/identity` |
| `aws/<tag>/` | each AWS release's record (`release.json`: PCRs, source commit, config commitment) and build inputs |
| `gcp/<tag>/` | each GCP release's record (`release.json`: image digest, source commit, config commitment) and build inputs |

Releases are built from `orbs-network/perpetual-hub` at the commit tagged `cosigner-b-<tag>`, with the kit in `ops/cosigner-enclave/` (see "A second kit instance" in its README). Production's co-signers publish to `orbs-network/enclave-config-1`.
