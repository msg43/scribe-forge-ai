# scribe-forge-ai

Audio transcription tool: Whisper for transcription, optional speaker diarization, output as JSON, TXT or Markdown. Commands are in the Makefile (`make help`). Code style and commit conventions are in AGENTS.md.

## Gotchas

- The diarization backend depends on the Python version. Resemblyzer is the default (in `requirements.txt`). pyannote.audio is optional (`requirements-optional-diarization.txt`) and is only enabled on Python below 3.12 (`PYANNOTE_ALLOWED` in `src/model_manager.py`).
- pyannote may need a Hugging Face token (`HUGGINGFACE_HUB_TOKEN`) and acceptance of the terms on the `pyannote/speaker-diarization-3.1` model page before the model downloads.
- On Windows, run through `run.ps1`. It activates the virtual environment, validates arguments, and takes the same arguments as `python main.py`. See `QUICK_START_WINDOWS.md`.
- `STRUCTURE.md` is stale: it says diarization uses PyAnnote, but the code tries Resemblyzer first.
