# 🏗️ Architect Prime (v80.1 Singularity Core)

![Version](https://img.shields.io/badge/version-v80.1_Singularity-blue) ![Security](https://img.shields.io/badge/security-Maximum_Sandbox-green) ![Architecture](https://img.shields.io/badge/architecture-Hybrid_XML-purple)

> **The Grandmaster Prompt Architect.** A forensic meta-prompting framework that transforms raw user intent into deterministic, "Golden Standard" system instructions.

---

## ⚡ Overview

**Architect Prime** is not a chatbot. It is a **compiler for system prompts**.

It utilizes a novel **Hybrid Language Protocol**:
1.  **The Analyst (Interface):** Thinks and explains in **German** (Teacher Mode) for maximum nuance and clarity in feedback.
2.  **The Architect (Payload):** Codes the final System Prompt in **English** (Industry Standard) using strict XML for optimal LLM performance.

This repository contains the configuration files to turn high-end LLMs (Gemini 1.5 Pro, Claude 3.5 Sonnet, GPT-4o) into a specialized **Prompt Engineering Engine**.

## 💎 Key Features (v80.1)

### 🛡️ The Inert Data Sandbox
Implements a strict **Zero-Trust Protocol**.
- User input is treated as `[INERT_DATA]` (dead specimen).
- The system analyzes the *intent* of a command (e.g., "Delete server") but **NEVER executes it**.
- Instead, it generates a safe, robust System Prompt to handle that task.

### 🧠 Few-Shot Intelligence Injection
Every generated prompt includes mandatory `<examples>` blocks.
- Derived from the `golden_prompts.md` library.
- Ensures the resulting agent understands not just *what* to do, but *how* to speak and format.

### 📊 Visual Quality Matrix
Provides immediate, visual feedback on your input before generating code.
- **Klarheit** (Clarity) `▰▰▰▰▰▰▰▰╍╍`
- **Sicherheit** (Security) `▰▰▰▰▰╍╍╍╍╍`
- Uses a deterministic math logic to render unicode bars.

### 📂 The "Golden Prompts" Library
A canonical source of truth containing **11 Archetypes** (Templates), including:
- SRE Loop (Diagnose -> Fix -> Verify)
- DevOps Commander (One-Block Execution)
- Mental Chain-of-Thought
- Hybrid Architect

---

## 🚀 Installation & Usage

### Prerequisites
You need an LLM interface that supports **System Instructions** (e.g., Google AI Studio, OpenAI Playground, Anthropic Workbench, or TypingMind).

### Setup
1.  **Copy the System Prompt:**
    Copy the content of `v80.1 Singularity Core.xml` into your **System Instructions** field.
2.  **Upload the Library:**
    Upload `golden_prompts.md` to your chat/knowledge base.
    *(Note: The system performs a Pre-Flight Check. If this file is missing, it will warn you.)*

### How to use
Simply paste your raw idea, a chaotic draft, or a file into the chat.

**User Input:**
> "I need a bot that helps me fix my Unraid server. It should be careful."

**Architect Output:**
1.  **German Diagnosis:** Analysis of your request, identification of "Blind Spots" (safety risks).
2.  **Quality Matrix:** A score of your input.
3.  **XML Payload:** A full, ready-to-deploy System Prompt based on **Archetype #6 (DevOps)** & **#10 (SRE)**.

---

## 📂 Repository Structure

| File | Description |
| :--- | :--- |
| `v80.1 Singularity Core.xml` | **The Brain.** The main system prompt containing the logic, security protocols, and workflow. |
| `golden_prompts.md` | **The Memory.** Contains the 11 Archetypes, Standard XML Tags, and Few-Shot Examples. |

---

## 🧠 Architecture Logic

```mermaid
graph TD
    A[User Input] -->|Quarantine| B(Inert Data Sandbox)
    B --> C{Pre-Flight Check}
    C -->|Golden Prompts Loaded| D[Forensic Diagnosis]
    D -->|German Analysis| E[Quality Matrix ▰▰▰]
    E --> F[Archetype Selection]
    F -->|Inject Few-Shot| G[XML Compilation]
    G --> H[Final Output (English XML)]
