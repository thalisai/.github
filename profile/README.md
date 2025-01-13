# Thalis AI Stack

[Please see the Thalis AI stack repository for more information.](https://github.com/thalisai/thalis-stack)

## Overview

The Thalis AI stack is an all-in-one platform for interactive original characters using open-source generative AI tools.
It offers multi-modal interactions, including text, audio, and image generation, from a single web interface. It can be
self-hosted, guaranteeing privacy and security, or run in the cloud on most common GPU providers.

The Thalis AI stack is designed with privacy and security at its core, avoiding cloud services in favor of self-hosted
and open-source tools to ensure your data remains under your control at all times.

Key features of the Thalis AI stack include:

<!-- no toc -->
- Self-hosted platform
- Modular, containerized architecture
- Using offline, open-source tools
- Multi-modal interactions including text, audio, and image generation
- Single web interface for all interactions
- Privacy and security focused
- Open-source license allowing for commercial use
- Multi-GPU support for parallel processing
- Distributed deployments for high availability
- Can be deployed on most common cloud providers and kubernetes
- Customizable image workflows
- Custom character commissions

[Visit the Thalis AI stack repository to get started.](https://github.com/thalisai/thalis-stack)

## Comparison

The Thalis AI stack is a collection of open-source tools that are distributed together, with everything you need to get
started and build your own interactive original characters.

Compared to other platforms and the individual tools, the Thalis AI stack offers more ways to interact with your
characters, while keeping your data private and secure. Support for custom LoRA networks allows you to customize your
characters in ways that are not possible with other platforms.

| Category                   | Thalis AI | Popular Chatbot Platforms | ComfyUI | Ollama  | open-webui |
| -------------------------- | --------- | ------------------------- | ------- | ------- | ---------- |
| Self-hosted                | Yes       | No                        | Yes     | Yes     | Yes        |
| Privacy & data control     | Yes       | No                        | Yes     | Yes     | Yes        |
| Completely open-source     | Yes       | No                        | Yes     | Yes     | Yes        |
| Runs on most common GPUs   | Yes       | No                        | Yes     | Yes     | Yes        |
| Text chat                  | Yes       | Yes                       | No (1)  | Yes (2) | Yes        |
| Audio generation           | Yes       | Yes                       | Yes (5) | No      | Yes        |
| Image generation           | Yes       | Yes                       | Yes     | No      | Yes        |
| Per-character image models | Yes       | No                        | Yes (3) | No (3)  | No         |
| Per-character text models  | Yes       | Yes                       | No (3)  | Yes (3) | Yes (4)    |
| Character LoRA networks    | Yes       | No                        | Yes     | Yes     | No         |
| Dynamic workflow generator | Yes       | No                        | No      | No      | No         |
| Image prompt generator     | Yes       | No                        | Yes (5) | No      | No         |
| Total                      | 12/12     | 4/12                      | 8/11    | 6/11    | 6/11       |

Notes:

1. ComfyUI has custom nodes that support text generation, but I am not aware of any that allow bidirectional chat
2. Ollama supports text chat through the command-line tools, but it does not include a web UI
3. ComfyUI and Ollama do not have character profiles, but they do allow you to choose the model for each chat or image
4. open-webui does not have character profiles, but it allows you to select the model for each chat
5. ComfyUI supports audio generation and image prompt generation with custom nodes

If you have another multi-modal AI stack that you would like to have included in this comparison, please let us know.
Other self-hosted stacks are especially welcome, we would love to support other privacy-conscious open-source projects.
