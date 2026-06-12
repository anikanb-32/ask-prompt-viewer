# Ask & Prompt Participant Data Viewer

Link to viewer: https://anikanb-32.github.io/ask-prompt-viewer/

Browse diary and in-lab interactions for each participant, view conversations in a chat interface, detect sycophantic responses, and continue conversations with an AI model.

## GitHub Pages (online, no server needed)

`index.html` is a fully static version that runs on GitHub Pages. It fetches data files directly and calls AI APIs from the browser.

**To enable GitHub Pages:**
1. Push this repo to GitHub
2. Go to **Settings → Pages** in your repo
3. Set Source to **Deploy from a branch**, branch `main`, folder `/` (root)
4. Your viewer will be live at `https://<username>.github.io/<repo-name>/`

## Local server (full features, private data)

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

## Project Structure

```
.
├── index.html         # Static viewer — works on GitHub Pages
├── viewer.py          # Local HTTP server (no external dependencies)
├── viewer.html        # Frontend for local server
├── participants.json  # Participant list for static viewer
├── P1/ … P11/
│   ├── diary_data/
│   │   ├── P*.json          # Interaction turns + annotations
│   │   └── P*_images/       # Photos from each diary interaction
│   └── inlab_data/
│       ├── P*_inlab.json
│       └── P*_inlab_images/
```
