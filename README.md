# Kiro Crew app template

The starting point for every Kiro Crew app repository. It carries the README
standard, the media-capture harness that produces the README's screenshots and
screen recording from a real Kiro Crew, the acceptance checklist, and CI.

| Path | What it is |
|---|---|
| `README.template.md` | The README standard: fixed sections and placeholders. Copy it to `README.md` |
| `CHECKLIST.md` | What a README must pass before it is published |
| `capture/` | The capture harness (`capture.py` and the offline model stand-in `stub_backend.py`), the README checker (`check_readme.py`) and an example `scenes.example.json`; see [capture/README.md](capture/README.md) |
| `docs/media/` | Where the captured pictures and walkthrough go |
| `.github/workflows/ci.yml` | Tests on every OS the manifest names, plus the README check |
| `LICENSE`, `NOTICE` | Apache License 2.0 |

## Start a new app repository from it

1. Copy everything here into the new repository and add the app (`app.json`,
   `backend/`, `agents/`, `skills/`, `tests/`, ...).
2. `cp README.template.md README.md` (this file is replaced) and
   `cp capture/scenes.example.json capture/scenes.json`.
3. Fill `capture/scenes.json` with fictional demo data seeded through the app's
   API, the screenshots (a hero, one per top use case) and a walkthrough.
4. Run `python capture/capture.py --kirocrew /path/to/KiroCrew`, then look at
   every image and a few video frames.
5. Write README.md from the code (never claim a feature the app lacks), run
   `python capture/check_readme.py`, and walk through CHECKLIST.md.
6. Delete `README.template.md` and `capture/scenes.example.json`.

The first repository built this way is
[kirocrew-app-personal-shopper](https://github.com/KiroCrewCaptain/kirocrew-app-personal-shopper).
