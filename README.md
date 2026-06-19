# Blog Writing Agent

A Streamlit + LangGraph project that generates blog posts from a topic, optionally researches the web, creates a draft outline, writes section-by-section markdown, and can place images into the final output.

## Overview

This project has two main parts:
- **Frontend**: a Streamlit UI for entering a topic, viewing progress, previewing markdown, and downloading blog outputs.
- **Backend**: a LangGraph pipeline that decides whether research is needed, plans the blog, writes sections, merges content, and generates image placeholders.

## Project Structure

- [frontend.py](frontend.py)  
  Streamlit app UI and markdown/image rendering.

- [backend.py](backend.py)  
  LangGraph workflow for router, research, planner, worker nodes, and image handling.

- [requirements.txt](requirements.txt)  
  Python dependencies needed to run the project.

## Features

- Topic-based blog generation
- Optional web research using Tavily
- Structured planning with section tasks
- Markdown preview and download
- Image plan and image download support
- Past blog loading from local `.md` files

## Required Setup

### 1. Python environment
Create and activate a virtual environment, then install dependencies:

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

### 2. Local model service
The backend expects a running local model service for the Ollama-based LLM setup. Start Ollama before running the app.

## Run the Application

```bash
streamlit run frontend.py
```

Then open the URL shown by Streamlit in your browser.

## How the Workflow Works

1. The app receives a topic and date from the UI.
2. The router decides if research is needed.
3. If needed, Tavily search results are gathered.
4. The orchestrator creates a content plan.
5. Worker nodes write each section in markdown.
6. The reducer combines sections and optionally inserts image placeholders.
7. The UI shows the plan, evidence, markdown preview, and generated images.

## Notes

- The app depends on external APIs and local model services, so generation quality depends on those services being available.
- Image generation is optional and may fail if the API credentials or model access are not configured correctly.
- The generated markdown and images are saved into the project folder for download.


