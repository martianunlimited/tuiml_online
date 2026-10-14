# 🌐 TuiML Online

[![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-Active-22c55e?logo=github)](https://martianunlimited.github.io/tuiml_online/)
[![WebAssembly](https://img.shields.io/badge/WebAssembly-WASM-6366f1?logo=webassembly)](https://webassembly.org/)
[![WebGPU](https://img.shields.io/badge/WebGPU-Hardware_Accelerated-06b6d4?logo=w3c)](https://www.w3.org/TR/webgpu/)
[![Pyodide](https://img.shields.io/badge/Python-Pyodide_0.26-ffd343?logo=python)](https://pyodide.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> **100% In-Browser Machine Learning Studio & Autonomous AI Data Scientist**  
> Powered by **WebAssembly (Pyodide)**, **WebGPU (Transformers.js)**, and **TuiML MCP Tools**.  
> **Zero backend servers • Zero API costs • Complete client-side privacy.**

🚀 **Live Web App**: [https://martianunlimited.github.io/tuiml_online/](https://martianunlimited.github.io/tuiml_online/)

---

## 💡 Overview

**TuiML Online** decouples machine learning and AI agent workflows completely from cloud infrastructure. By compiling Python and the TuiML machine learning toolkit into WebAssembly and executing quantized LLMs via WebGPU, every visitor's browser becomes an independent, self-contained AI lab.

### Why TuiML Online?

1. **$0 Hosting & Server Bills**: No backend Python APIs, no Celery queues, no cloud GPU instances. GitHub Pages serves static files over global CDN for free.
2. **Infinite Horizontal Scale**: 1 user or 1,000,000 users — your server load remains at **0% CPU**. Every user computes on their own hardware.
3. **Absolute Data Privacy (HIPAA / GDPR)**: Uploaded CSVs, trained models, and LLM conversations **never leave your computer**. Nothing is transmitted over the network.
4. **Offline Ready**: Once cached in your browser (`IndexedDB`), the application, models, and ML algorithms function without an internet connection.

---

## ⚡ Core Architecture

```
┌────────────────────────────────────────────────────────────────────────┐
│                        USER'S WEB BROWSER TAB                          │
├───────────────────────────────┬────────────────────────────────────────┤
│           THE BRAIN           │               THE HANDS                │
│       WebGPU / Transformers.js│             Pyodide / WASM             │
│                               │                                        │
│   Quantized Local LLM         │        TuiML ML Engine & MCP Tools     │
│   • Qwen2.5-0.5B-Instruct     │        • tuiml_train                   │
│   • Qwen2.5-1.5B-Instruct     │        • tuiml_predict                 │
│   • Google Gemma-2-2B-IT      │        • tuiml_benchmark               │
│   • Qwen2.5-Coder-1.5B        │        • tuiml_describe                │
│   • SmolLM2-360M-Instruct     │        • tuiml_plot                    │
├───────────────────────────────┴────────────────────────────────────────┤
│                       IN-MEMORY MCP ROUTER                             │
│     JavaScript bridges JSON-RPC tool calls directly into Pyodide       │
│     Zero HTTP latency • Zero server costs • Zero data transmission     │
└────────────────────────────────────────────────────────────────────────┘
```

---

## ✨ Features

- **🤖 In-Browser Autonomous AI Data Scientist**:
  - Load quantized Q4/q4f16 LLMs (`Qwen2.5`, `Gemma-2-2B`, `SmolLM2`) into client VRAM via WebGPU.
  - Automatically queries available TuiML MCP tools to train models, run benchmarks, and explain findings.
- **🌲 Pure-WASM Machine Learning (TuiML)**:
  - Decision Trees, Random Forests, Naive Bayes, Logistic Regression, KNN, and KMeans clustering.
  - Pure-Python, NumPy, and SciPy graceful fallbacks running at near-native speed.
- **📁 Drag-and-Drop CSV Uploader**:
  - Load custom tabular CSV files directly into Pyodide's virtual filesystem (`MEMFS`).
  - Automatically profiles rows, columns, and target labels.
- **📊 2D Decision Surface Visualizer**:
  - Matplotlib decision boundary visualization rendered directly to base64 images client-side.
- **💻 Embedded Python REPL & Notebook**:
  - Interactive terminal with preset workflows, <kbd>Tab</kbd> indentation, <kbd>Ctrl+Enter</kbd> execution, and live stdout capture.

---

## 🛠️ Local Development & Testing

Run any local static file server from the root of this project:

```bash
# Python
python3 -m http.server 8000

# Node.js
npx serve .
```

Open `http://localhost:8000/` in Chrome, Edge, Safari, or Firefox.

---

## 🚀 GitHub Pages Deployment

This repository includes an automated GitHub Actions deployment workflow ([`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)).

To enable hosting on your repository:
1. Go to your repository on GitHub: `https://github.com/martianunlimited/tuiml_online`.
2. Navigate to **Settings** → **Pages**.
3. Under **Build and deployment** → **Source**, select **GitHub Actions**.
4. Every push to `main` will automatically build and publish the live site.

---

## 📜 License

MIT License. Built with [TuiML](https://tuiml.ai), [Pyodide](https://pyodide.org), and [Transformers.js](https://huggingface.co/docs/transformers.js).
