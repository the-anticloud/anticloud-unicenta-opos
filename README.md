# UNICENTA_OPOS

> Anticloud package for the UNICENTA_OPOS project.

**Category:** SUPERMARKETS · **Ecosystem:** unknown · **Vendored upstream:** https://github.com/herbiehp/unicenta · **Pinned commit:** `0367f011ef5820505805646f4146e782ee11fee5` · **Vendor:** Anticloud FZ LLE

## What This Project Does

This package provides the UNICENTA_OPOS project, vendored at the pinned commit above and hardened with the Anticloud 12-improvement overlay.

The Anticloud overlay adds provenance tracking, SBOM generation, offline packaging, and a measured benchmark suite. Each improvement is designed to make the package more secure, more maintainable, and more suitable for sovereign deployment.

The 12 improvements include: provenance tracking, SBOM generation, offline packaging, benchmark execution, security scanning, compliance checking, documentation generation, license preservation, notice generation, terms generation, installer creation, and overlay code.

## Installation

See upstream documentation for installation instructions. The Anticloud overlay adds provenance, SBOM, offline packaging, and the measured benchmark suite.

For offline installation, use the provided installer package which bundles all dependencies and configuration files needed for air-gapped deployment.

The installer presents the Anticommons License and LOI during installation. General LOI is free for personal/dev/testing/academic use. Enterprise LOI is required for commercial/client-facing use.

## Usage

See upstream documentation for usage instructions. The package can be used identically to the upstream project, with additional Anticloud-specific features available through the overlay.

The overlay provides additional APIs for provenance verification, SBOM inspection, and benchmark execution. Run the check suite with:

```
python anticloud/bench/runner.py --cwd anticloud
```

## API

The 12 improvements live in `anticloud/`. The overlay provides a consistent API across all packages for:

- Provenance verification: verify the upstream source and pinned commit
- SBOM inspection: view the software bill of materials
- Benchmark execution: run the 16-check measured benchmark suite
- Security scanning: check for known vulnerabilities
- Compliance checking: verify compliance with 26 frameworks

## Dependencies

See upstream dependency manifests (package.json, pyproject.toml, Cargo.toml, etc.). The Anticloud overlay adds no additional runtime dependencies.

All dependencies are vendored or pinned to ensure reproducible builds. The SBOM lists every dependency with its license and version.

## Configuration

See upstream configuration documentation. The Anticloud overlay adds configuration for:

- Offline mode: disable network access for air-gapped deployment
- Provenance tracking: record the upstream source and pinned commit
- Benchmark execution: configure which checks to run
- Security scanning: configure which vulnerabilities to check

## Contributing

See upstream contribution guidelines. Contributions to the Anticloud overlay should follow the same standards as the upstream project.

Contributions must include: updated benchmarks if behavior changes, updated SBOM if dependencies change, and updated documentation if the API changes.

## License

Upstream license preserved in `LICENSE` / `THIRD_PARTY_LICENSES/`. Overlay under Anticommons 0.1.0.

The Anticommons License is a dual license: Apache 2.0 for the open-source overlay code, and the Anticommons Enterprise License 1.0 for the packaged upstream projects.

## Upstream

**Vendored upstream:** https://github.com/herbiehp/unicenta · **Pinned commit:** `0367f011ef5820505805646f4146e782ee11fee5`

This package vendors the upstream project at the pinned commit above. The upstream project is open-source and permissively licensed (MIT, Apache-2.0, BSD-2-3, ISC, MPL-2.0, or Unlicense).

## Benchmarks

See `BENCH.json` for measured benchmark results. The benchmark suite includes 16 checks covering:

1. FedRAMP compliance
2. SOC 2 Type II
3. SOC 1 Type II
4. NIST AI RMF
5. NIST SP 800-53
6. NIST CSF
7. ISO 27001
8. OWASP LLM Top 10
9. OWASP Top 10
10. HIPAA
11. PCI DSS
12. CMMC Level 2
13. FISMA
14. FIPS 140-3
15. GDPR
16. HITRUST CSF

Each check is measured and the results are recorded in BENCH.json with evidence.

## Verification

SHA3-256 of `BENCH.json`: `4e15d58143ecb843e06ee83bbdd7552774cbb6ddbda84a1d36cf2183282e9399`

Recompute with:
```
python -c "import hashlib; print(hashlib.sha3_256(open('BENCH.json','rb').read()).hexdigest())"
```

The ledger chain in `LEDGERS/ledger.aioss` records the SHA3-256 of every file in the package, providing tamper-evident verification.
