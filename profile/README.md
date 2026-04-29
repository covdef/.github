<h1 align="center">CovDef</h1>

<p align="center">
  Compression, steganography, and verification systems for private communication on real devices.
</p>

<p align="center">
  <strong>Mobile-first</strong> · <strong>deterministic when it matters</strong> · <strong>measured against actual compression ratios</strong>
</p>

---

## What This Organization Builds

CovDef is a research-and-engineering workspace for hiding, compressing, verifying, and transporting payloads through ordinary-looking communication surfaces.

The work is split into focused repos instead of one mixed experimental folder:

| Repo | Scope |
| --- | --- |
| [`stego`](https://github.com/covdef/stego) | LLM text steganography, Modal services, relays, benchmarks, and decode tests. |
| [`compression-decompression`](https://github.com/covdef/compression-decompression) | LLM/RWKV compression experiments, llama-zip work, Android cross-device tests, and deterministic decompression tooling. |
| [`disclaimer`](https://github.com/covdef/disclaimer) | Corporate-disclaimer watermarking, fingerprint tokens, endpoint tests, and entropy analysis. |
| [`email-entropy`](https://github.com/covdef/email-entropy) | Email watermarking, verification, arithmetic-coding variants, and backend benchmarks. |
| [`f5-tts`](https://github.com/covdef/f5-tts) | F5-TTS Modal backend for voice cloning and speech generation experiments. |

Most repositories are private while the implementation is still being validated.

## Engineering Direction

The core constraint is not just whether a model can compress or encode data. The harder requirement is whether a payload can survive independent encode/decode paths across devices, runtimes, and hardware backends.

Current priorities:

- Cross-phone deterministic compression and decompression.
- Practical stego payload recovery from natural generated text.
- Watermark/fingerprint schemes that can be verified without fragile hidden state.
- Modal-hosted GPU services with short warm-container windows and reproducible APIs.
- Mobile and constrained-device tests before assuming a desktop result generalizes.

## Design Rules

- Prefer exact reproducibility over impressive demos that only work on one machine.
- Keep model weights, caches, logs, and device-specific secrets out of Git.
- Treat compression ratio, round-trip success, and cross-device hash agreement as first-class metrics.
- Separate experimental probes from deployable service code.
- Document every setup path so a second device can reproduce the result.

## Status

This is active applied research. Some repos contain working services; others contain controlled experiments used to decide what should be promoted into production code.

If you are joining the project, start with the repo matching your task and read its local `README.md` first.
