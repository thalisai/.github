# Thalis AI

Original-character LoRA models and the tools that shape them.

## What we build

**Thalis AI** is a studio focused on original-character LoRA training for Flux, Illustrious, and SDXL. We create dark fantasy and cosmic horror art through a fully self-hosted pipeline — from dataset curation and model training to image generation and release.

The work lives at the intersection of classical fantasy illustration and modern generative models: original characters with weight and presence, built in worlds of green stone and radium light.

All models are trained from original datasets. No likenesses of real people. No scraped IP.

## Our tooling

We don't just consume the open-source ecosystem — we bend it to our workflow.

### Custom ComfyUI nodes

The model lifecycle runs inside ComfyUI, extended with our own custom node package:

- **REST endpoints** for listing, promoting, downloading, and serving `.safetensors` files directly from the ComfyUI LoRA directory
- **VRAM management nodes** — unload all models and clear CUDA cache inline in a workflow, so you can switch between Flux and SDXL base models without restarting the ComfyUI pod
- Path-traversal guards, type-directory whitelisting (`testing` / `release` / `third_party` / `recipes`), and atomic download-to-temp semantics

The node runs inside the ComfyUI process with full filesystem access, which means external orchestrators (SSH callers, API clients) can manage LoRAs without needing pod-level write permissions.

### Forked training toolkit

Our LoRAs are trained on a fork of [AI-Toolkit](https://github.com/ostris/ai-toolkit) with patches accumulated across 700+ production training runs:

- **Additional optimizers** — prodigy-plus-schedule-free, schedule-free variants, and others beyond the upstream defaults
- **Validation loss tracking** — proper train/val split support in the dataloader, with per-epoch validation reporting
- **Lookahead wrapper** — optional lookahead flag for smoother optimizer convergence
- **DataLoader fixes** — `Subset` attribute handling, backend passthrough to custom optimizers, empty-dataset guards
- **W&B integration fixes** — TTY detection and local-sample retention flags

## Where to find the work

- **Model catalog**: [thalis.dev](https://thalis.dev) — 168+ concepts, 294+ released versions
- **Civitai**: [thalisai](https://civitai.com/user/thalisai) — public LoRA releases with showcase galleries
- **DeviantArt**: [thalisai](https://www.deviantart.com/thalisai)
- **Bluesky**: [@thalis-ai.bsky.social](https://bsky.app/profile/thalis-ai.bsky.social)

## Open source

Our training and inference tooling is open-source:

| Repo | What it is |
|------|-----------|
| [`thalismind/ai-toolkit`](https://github.com/thalismind/ai-toolkit) | Forked training toolkit with additional optimizers, validation split, and 700+ runs of patches |
| [`thalismind/agentic-workgraph`](https://github.com/thalismind/agentic-workgraph) | Workflow orchestration for agentic tasks — the scheduler behind our pipeline automation |
| [`thalismind/lora-notebooks`](https://github.com/thalismind/lora-notebooks) | Jupyter notebooks for LoRA training experiments, dataset prep, and model evaluation |
| [`thalismind/caption-notebooks`](https://github.com/thalismind/caption-notebooks) | Captioning pipelines and tools for training dataset preparation |

The `thalis-stack` chatbot project has been deprecated. The work now lives in the focused tools above, built directly on ComfyUI and our forked AI-Toolkit.

If you're building your own pipeline and want to talk shop, reach out. We share what we've learned.

## Infrastructure

The studio runs on a self-hosted Kubernetes cluster with ComfyUI, Ollama, ChromaDB, Matrix bridges, and Prometheus/Grafana monitoring. Everything stays on our own hardware — from training to inference to publishing.
