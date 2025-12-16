**Project Overview**

- **What:** a small data-extraction + analysis project that uses the Spotify and Last.fm APIs to collect songs (2010–2018) and produce CSVs/analysis. Primary code lives in the Jupyter notebook `spotipy.ipynb` and the output CSV is `canciones_2018.csv`.
- **Why:** the notebook extracts artists/albums/tracks by genre and year, enriches artists with Last.fm metadata, then stores results for later analysis and visualization.

**Quick Setup**

- **Dependencies:** this project requires `spotipy`, `python-dotenv`, `pandas`, and `requests`. Install locally with:

```
pip install spotipy python-dotenv pandas requests jupyterlab
```

- **Environment:** the notebook expects these environment variables:
  - `SPOTIFY_CLIENT_ID`
  - `SPOTIFY_CLIENT_SECRET`
  - `API_KEY_LASTFM`
  - `SHARED_SECRET_LASTFM` (used by some Last.fm calls if implemented)

Store them in a `.env` file when working locally (the notebook already calls `load_dotenv()`).

**Key Files & Patterns**

- `spotipy.ipynb` — single source of truth: extraction logic, API calls, and CSV export. Inspect the following patterns:
  - Spotify auth: `SpotifyClientCredentials(...)` then `sp = spotipy.Spotify(auth_manager=mis_credenciales)` — use the `sp` client consistently across cells.
  - Genre loop: the notebook builds `generos = ["flamenco","latin","jazz","rock"]` and iterates to collect albums/tracks for a given `año` (default 2018).
  - Duplicate prevention: `albumes_ya_vistos = set()` is used to avoid repeated album processing — keep this pattern when adding more queries.
  - Last.fm enrichment: see `busqueda_info_artista(nombre_artista, api_key_lastfm)` which encodes artist names with `quote()` and calls Last.fm via `requests`.

**Project-specific gotchas / fixes**

- Variable name consistency: some cells create `sp` but later code references `spotify` (e.g., `resultado_artistas = spotify.search(...)`). Prefer `sp` throughout to avoid NameError when running cells sequentially.
- Function return pattern: `busqueda_info_artista` sets `artista_info = data['artist']` inside the function but does not return it. Prefer returning the value rather than mutating a global. Example fix:

```
def busqueda_info_artista(nombre_artista, api_key_lastfm):
    q = quote(nombre_artista)
    url = f"http://ws.audioscrobbler.com/2.0/?method=artist.getinfo&artist={q}&api_key={api_key_lastfm}&format=json"
    resp = requests.get(url, timeout=10)
    resp.raise_for_status()
    data = resp.json()
    return data.get('artist')
```

- Global vs local names: the notebook defines `artista_info = []` at top-level then assigns `artista_info = data['artist']` inside the function — avoid shadowing globals; use returns and local variables.
- CSV output: the code writes `todas_las_canciones_df.to_csv("canciones_2018.csv", index=False)` to repo root. When testing, watch for accidental overwrites.

**How to run / debug**

- Open the notebook in VS Code or Jupyter: `jupyter lab` or run the notebook in VS Code's Interactive window.
- If a cell errors with a missing name (e.g., `spotify` not defined), re-run the auth cell that sets `sp = spotipy.Spotify(...)` and then re-run dependent cells.
- Network calls: API requests have a 10s timeout in the notebook. If you hit rate limits, add `time.sleep()` between requests or use smaller `limit` values on searches.

**Conventions & language**

- Code and variables use Spanish identifiers (e.g., `generos`, `todas_las_canciones`, `albumes_ya_vistos`). Keep this style when adding cells to keep readability consistent across the notebook.
- Prefer small, pure helper functions that return data (so they are easy to test). Example: replace globals with `get_artist_info(...) -> dict`.

**Integration points**

- Spotify: authenticated via `SpotifyClientCredentials` — all queries come from the `spotipy` client.
- Last.fm: simple HTTP calls to `ws.audioscrobbler.com` using `requests`; API key read from env.

**When editing**

- Edit `spotipy.ipynb` (not a .py file). Keep changes small per cell and re-run the notebook top-to-bottom to validate stateful clients (`sp`, `api_key_lastfm`).
- If you add scripts, include a `requirements.txt` or `pyproject.toml` and update this file with install commands.

**Commands reference**

- Install deps: `pip install spotipy python-dotenv pandas requests jupyterlab`
- Start dev UI: `jupyter lab` or open `spotipy.ipynb` in VS Code.

If anything in this guidance is unclear or you want conventions stricter (naming, function style, tests), tell me which parts to expand and I will iterate.
