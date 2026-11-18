# Xcelerator cache shard

Immutable numerical artifacts in the public Xcelerator cache.

Managed by the [Xcelerator Toolkit](https://github.com/TeamXcelerator/xcelerator-toolkit).

## Reading artifacts

Canonical artifact manifests use content model v2, requiring Toolkit v0.17.1 or a compatible newer reader. Numerical keys describe the producing request and its numerical inputs. Toolkit release labels and provenance do not define numerical identity; producer and reader eligibility are checked separately. Target-function inputs and target-derived artifacts are private-only.

## Layout

```text
objects/sha256/<prefix>/<digest>.part
manifests/<semantic-prefix>/<manifest-digest>.json
encodings/<payload-prefix>/<encoding-digest>.json
indexes/<family>/<semantic-prefix>.json
attestations/validation/<digest>.json
transactions/batches/<batch-id>/<visibility>.json
ledger/capacity.json
```

Routing and capacity policies are defined by the [cache registry](https://github.com/TeamXcelerator/xcelerator-cache-public-registry). The shard capacity ledger accounts for its retained payloads and metadata.

Payload hashes, publication records and validation evidence are checked by the Toolkit before reuse. Duplicate selection requires matching numerical identity, validated payload, visibility, scope and assurance; the latest original publication wins equivalent ties.

Maintainer: Ronnie Andrews, Jr. (Team Xcelerator Inc.).

License: see [LICENSE](LICENSE).

"Team Xcelerator Inc." is a registered trademark of Team Xcelerator Inc.
