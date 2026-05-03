# Tencent Capstone Project: AI-Assisted Oral History & Memoir Generation

This repository hosts the capstone project developed in collaboration with **Tencent**, focusing on **AI-Assisted Oral History and Memoir Generation**. The core objective is to integrate old photographs, interview dialogues, and narrative generation into a cohesive workflow. This project serves as a comprehensive workspace for practical demonstration, extensible evaluation, and ongoing data/research accumulation.

Rather than a single application, this repository comprises several interconnected components: a main system, evaluation frameworks, simulation pipelines, and archival materials.

## Project Overview

This project addresses three primary challenges:

1.  **Interviewer Simulation**: How to automatically generate questions based on old photographs that sound like a human "interviewer" rather than a robotic form filler.
2.  **Narrative Synthesis**: How to integrate visual information and oral responses after multi-turn dialogues into a natural, coherent story.
3.  **Evaluation Framework**: How to design reusable benchmarks, simulated data, and scoring methodologies to systematically compare different model versions.

The repository is structured into three distinct layers:
*   **Demonstration Layer**: A photo-story generation system designed for live showcasing.
*   **Research Layer**: Methodological explorations into follow-up questioning mechanisms, story quality, and evaluation metrics.
*   **Data Layer**: Organized collections of simulated samples, interview transcripts, memoir drafts, and benchmark documentation.

## Core Capabilities

The main application, centered around the **"Photo Story"** demo, currently supports:

*   **Single-Image Deep Dive**: Visual analysis, interview questioning, and story generation for individual photos.
*   **Multi-Image Narrative Chain**: Connecting multiple photos into a cross-timeline life narrative.
*   **Enhanced Follow-up Mechanism**: Dynamically adjusting questioning strategies based on response quality, emotional cues, and information gaps.
*   **Story Generation**: Synthesizing photo analysis and interview content into first-person or stylized narrative texts.
*   **Web Demonstration**: A full-stack frontend and backend API for interactive showcasing.
*   **Text Evaluation**: Dimensionalized scoring capabilities for generated stories.
*   **Benchmarking & Simulation**: Dedicated directories and documentation for future experiments and benchmarks.

**Note on Models**: The default backend is now unified to use **Tencent HunYuan**. Documentation, environment variable examples, and running instructions are configured primarily for HunYuan. Logic for Gemini is retained only for backward compatibility and is no longer the recommended default.

## Repository Structure

Key directories include:

*   [`demo/`](demo): The main application directory. Contains CLI entry points, Flask API, frontend code, and core Python modules.
*   [`benchmark/`](benchmark): Evaluation methodologies, team guides, and reference materials for story generation benchmarks.
*   [`simulation/`](simulation): Simulated data, configuration files, scripts, and pipeline drafts.
*   [`image/`](image): Project-related image assets and output resources.
*   `Memoir_Draft_Interview_Zhiqing.md`: Sample memoir text (Educated Youth).
*   `Memoir_Draft_Interview_Rural_Teacher.md`: Sample interview and draft material (Rural Teacher).
*   `Memoir_Draft_Interview_Self_Employed.md`: Sample character story material (Self-Employed).
*   `Memoir_Interview_Index.md`: Index for the three sample materials.

> **Tip**: If you only want to run and demonstrate the system, start directly with [`demo/README.md`](demo/README.md).

## Main Application Details

The [`demo/`](demo) directory is the most complete and ready-to-run part of this repository, featuring:

*   **CLI Interaction**: Mode selection, image upload, interview flow, and story generation.
*   **Backend API**: Provides capabilities for analysis, questioning, generation, and scoring.
*   **Frontend Interface**: For uploading photos, conducting interviews, and displaying results.
*   **Core Modules**: Image analysis, question generation, context management, story generation, and evaluation agents.

**Key Entry Points**:
*   [`demo/main.py`](demo/main.py): Main entry for CLI interaction.
*   [`demo/server.py`](demo/server.py): Flask backend entry point.
*   [`demo/judge_story.py`](demo/judge_story.py): Entry point for story text evaluation.
*   [`demo/src/question_generator.py`](demo/src/question_generator.py): Logic for question generation and follow-ups.
*   [`demo/src/enhanced_followup.py`](demo/src/enhanced_followup.py): Enhanced follow-up strategy module.

## Quick Start

There are two common ways to use this project.

### 1. Run the Main Application

Refer to [`demo/README.md`](demo/README.md) for detailed instructions. Common steps:

```bash
cd demo
pip install -r requirements.txt
python main.py
```

**Important**: Before running, configure the Tencent HunYuan environment variables in [`demo/.env`](demo/.env), specifically `HUNYUAN_API_KEY`. The main workflow will not function correctly without this key.

To run the **Web Demo**:

```bash
# Terminal 1: Start Backend
cd demo
pip install -r requirements.txt
python server.py

# Terminal 2: Start Frontend
cd demo/frontend
npm install
npm run dev
```

### 2. Explore Benchmarks & Research Materials

If you are interested in experimental design, metric definition, or research directions, prioritize these documents:

*   [`benchmark/HANNA_BENCHMARK_TEAM_GUIDE.md`](benchmark/HANNA_BENCHMARK_TEAM_GUIDE.md)
*   [`benchmark/HANNA_BENCHMARK_METRICS_AND_METHODS.md`](benchmark/HANNA_BENCHMARK_METRICS_AND_METHODS.md)
*   [`benchmark/STORY_GENERATION_BENCHMARK_REFERENCE.md`](benchmark/STORY_GENERATION_BENCHMARK_REFERENCE.md)
*   [`simulation/README_STEPS.md`](simulation/README_STEPS.md)

## Repository Status Note

This repository recently underwent a structural refactor. Application code previously located in the root directory has been moved into the [`demo/`](demo) directory. Consequently:

*   The GitHub repository homepage README is in the **root**.
*   Actual running instructions and application details are in **[`demo/README.md`](demo/README.md)**.
*   `benchmark`, `simulation`, and sample materials remain as parallel directories.

*Note: If you encounter old Pull Requests referencing `main.py`, `config.py`, or `src/` in the root directory, they are based on the old structure and do not reflect the current main branch organization.*

## Suggested Reading Order

For first-time visitors, the recommended reading order is:

1.  [`demo/README.md`](demo/README.md)
2.  [`demo/main.py`](demo/main.py)
3.  [`demo/src/question_generator.py`](demo/src/question_generator.py)
4.  [`benchmark/HANNA_BENCHMARK_TEAM_GUIDE.md`](benchmark/HANNA_BENCHMARK_TEAM_GUIDE.md)
5.  [`simulation/README_STEPS.md`](simulation/README_STEPS.md)

This sequence provides the clearest understanding of the relationships between "Application Demo," "Follow-up Research," "Evaluation Design," and "Simulated Data" within this project.
