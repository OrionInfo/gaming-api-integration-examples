# Illustrative FastAPI patterns

These snippets demonstrate request validation and a mock health endpoint. They are educational fragments, not a complete wallet or gaming integration. No real provider calls or credentials are used.

## Minimal mock endpoint
```python
from fastapi import FastAPI
from pydantic import BaseModel, Field

app = FastAPI(title="Demo Integration API")

class LaunchRequest(BaseModel):
    player_ref: str = Field(min_length=1, max_length=64)
    game_ref: str = Field(min_length=1, max_length=64)

@app.get("/health")
def health():
    return {"status": "ok", "mode": "mock"}

@app.post("/demo/launch")
def launch(payload: LaunchRequest):
    # Fictional response only; no external launch occurs.
    return {
        "status": "accepted",
        "session_ref": "sess_demo_3001",
        "player_ref": payload.player_ref,
        "game_ref": payload.game_ref,
        "launch_url": "https://example.invalid/demo"
    }
```

## Run locally
```bash
python -m venv .venv
# Activate the environment for your operating system, then:
pip install fastapi uvicorn
uvicorn app:app --reload
```
Save the snippet as `app.py`. The `.invalid` domain is reserved for examples. Do not expose this mock endpoint publicly or use it to process real accounts, balances, or transactions.
