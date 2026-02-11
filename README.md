# Combination of Video + Text LLM
Multimodal Video–Image–Text Large Language Model (PyTorch)

## Overview
This repository contains a from-scratch, research-oriented implementation of a Video-LLaVA–style multimodal large language model, combining a LLaMA-based causal language model with CLIP-style vision encoders for images and videos. The project emphasizes architectural clarity, checkpoint compatibility, and transparent low-level implementation.

It serves as an educational and experimental framework for understanding how modern multimodal LLMs integrate vision, video, and language.

## Core Idea
This project reimplements the core components of Video-LLaVA without relying on high-level abstractions, enabling deep inspection and customization of:

- LLaMA-style transformer blocks  
- CLIP vision encoders for images and videos  
- Multimodal projection and fusion layers  
- Autoregressive text generation with visual context  

The implementation is designed to remain faithful to official checkpoints while being research-friendly and extensible.

## System Capabilities

### Language Model (LLaMA)
- Decoder-only causal transformer  
- RMSNorm and Rotary Positional Embeddings (RoPE)  
- Multi-head self-attention with KV caching  
- Autoregressive text generation  
- Hugging Face weight compatibility  

### Vision & Video Encoding (CLIP)
- Patch-based image embeddings  
- Vision Transformer encoder  
- Support for both image and video inputs  
- Frame-wise video feature aggregation  
- Configurable vision architecture  

### Multimodal Fusion
- Vision token placeholders  
- Learned projection from vision to text space  
- Dynamic replacement of special vision tokens  
- Unified attention over text and visual tokens  

### Model Inspection & Diagnostics
- Parameter counting and memory profiling  
- Safetensors weight loading and validation  
- CUDA memory tracking  
- Meta-device initialization for low-memory loading  
- Structural parity checks with HF checkpoints  

## High-Level Architecture

### Core Components
- **Text Tower**: LLaMA-style causal language model  
- **Image Tower**: CLIP Vision Transformer  
- **Video Tower**: CLIP Vision Transformer (shared or separate)  
- **Multimodal Projector**: Vision-to-text embedding alignment  
- **Fusion Logic**: Token-level merging of vision and text streams  

The architecture mirrors production multimodal LLMs while remaining fully readable and extensible.

## Design Principles
- From-scratch PyTorch implementation  
- Minimal reliance on black-box abstractions  
- Explicit tensor shapes and data flow  
- Checkpoint compatibility over convenience  
- Research-first design  

## Workflow Summary
1. Load and inspect Video-LLaVA configuration  
2. Initialize lightweight test configurations  
3. Build LLaMA, CLIP, and multimodal modules manually  
4. Validate tensor shapes and forward passes  
5. Load Hugging Face safetensors weights  
6. Verify key alignment and memory usage  
7. Run multimodal generation with image or video inputs  

## Technology Stack
- **Language**: Python  
- **Framework**: PyTorch  
- **Model Hub**: Hugging Face  
- **Checkpoint Format**: Safetensors  
- **Hardware**: CUDA-enabled GPUs  

## Intended Use Cases
- Multimodal LLM research and education  
- Understanding Video-LLaVA internals  
- Architecture and fusion experimentation  
- Weight-loading and memory optimization studies  
- Teaching vision–language model design  

## License
This project is intended for research and educational purposes.  
Please refer to the original Video-LLaVA and LLaMA licenses for checkpoint usage and redistribution constraints.
