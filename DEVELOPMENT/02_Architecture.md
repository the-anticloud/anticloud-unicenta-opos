# Technical Architecture — UNICENTA_OPOS

**Upstream:** [https://github.com/uniCenta/uniCenta-oPOS](https://github.com/uniCenta/uniCenta-oPOS)
**License:** GPL/MIT
**Category:** POS_SYSTEMS
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

Enterprise-grade Java POS

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local product recommendation at checkout — no cloud
2. AIOSS tamper-evident transaction audit chain (PCI DSS aligned)
3. AES-256 P2PE for all payment data
4. Single-binary POS executable — works on any x86/ARM hardware
5. Zero-cloud: full offline transaction processing and receipt generation
6. GPU/CPU equalizer: AI upsell on CPU for embedded POS hardware
7. Zero-telemetry: removes all third-party analytics from POS
8. Open EMV integration: no proprietary payment SDK required

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_unicenta_opos.spec` or `go build -o unicenta_opos`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |