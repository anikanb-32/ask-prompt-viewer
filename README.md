# Ask & Prompt — Participant Data Viewer

An interactive browser-based viewer for the Ask & Prompt study dataset. Browse diary and in-lab interactions for each participant, view conversations in a chat interface, detect sycophantic responses, and continue conversations with an AI model.

## Features

- Browse all participants (P1–P11) across diary and in-lab sessions
- Chat-style conversation view with inline images
- Sycophancy detection — flags interactions where Be My AI aligns with user opinion over factual accuracy
- Continue any conversation using GPT-4o, Claude, or Gemini (full image + text context sent)
- Save flagged interactions to a personal folder (persisted in browser localStorage)

## Setup

**Requirements:** Python 3.8+, no external packages needed.

```bash
# 1. Clone the repo
git clone <repo-url>
cd Ask-Prompt_Participants_data

# 2. (Optional) Set API keys as environment variables
export ANTHROPIC_API_KEY="sk-ant-..."
export OPENAI_API_KEY="sk-..."
export GEMINI_API_KEY="AIza..."

# 3. Run the viewer
python3 viewer.py
```

Then open [http://localhost:8765](http://localhost:8765) in your browser.

API keys can also be entered through the ⚙ settings modal in the viewer UI — no restart required.

## Project Structure

```
.
├── viewer.py          # Local HTTP server (no external dependencies)
├── viewer.html        # Frontend — chat UI, sycophancy analysis, saved folder
├── P1/ … P11/
│   ├── diary_data/
│   │   ├── P*.json          # Interaction turns + annotations
│   │   └── P*_images/       # Photos from each diary interaction
│   └── inlab_data/
│       ├── P*_inlab.json
│       └── P*_inlab_images/
```

## API Keys

Keys are **never stored on disk** — they live in server memory and clear on restart. You can set them via environment variables (recommended) or paste them into the ⚙ modal at runtime.
