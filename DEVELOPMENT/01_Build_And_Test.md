# Build and Test

**Project:** `UNICENTA_OPOS`
**Upstream:** https://github.com/uniCenta/uniCenta-oPOS
**License:** GPL/MIT

## Quick Start

```bash
git clone https://github.com/uniCenta/uniCenta-oPOS
cd uniCenta-oPOS
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local product recommendation at checkout — no cloud
2. AIOSS tamper-evident transaction audit chain (PCI DSS aligned)
3. AES-256 P2PE for all payment data
4. Single-binary POS executable — works on any x86/ARM hardware
5. Zero-cloud: full offline transaction processing and receipt generation
6. GPU/CPU equalizer: AI upsell on CPU for embedded POS hardware
7. Zero-telemetry: removes all third-party analytics from POS
8. Open EMV integration: no proprietary payment SDK required

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
