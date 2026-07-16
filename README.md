# Mixory

Mixory reshapes a playlist or pasted tracklist into a smoother DJ-style flow for Apple Music AutoMix and Spotify Mix.

It is designed for music lovers and beginner DJs who want a playlist order that feels more natural: cleaner track identity, estimated genre balance, BPM/key hints, an energy curve, and a recommended sequence that prioritizes smooth transitions.

## Live Site

- Frontend: https://mixoryflow.com
- Backend health check: https://api.mixoryflow.com/api/health

## What It Does

- Accepts pasted tracklists, TXT files, CSV files, Exportify exports, Apple Music playlist exports, and TuneMyMusic exports.
- Parses common formats such as `Artist - Track`, `Track - Artist`, `Track by Artist`, and playlist CSV rows.
- Analyzes the source list for rough genre balance, BPM range, mood direction, and set length fit.
- Generates a DJ-style playlist flow with an energy curve and transition notes.
- Supports optional DJ/mood references, must-have tracks, and extra direction notes.
- Lets users adjust track order manually and export simple or detailed TXT versions.

## Data Sources

Mixory combines several lightweight metadata sources and local reference-set patterns:

- MusicBrainz recording search for track and artist identity matching.
- GetSongBPM for BPM/key enrichment when `GETSONGBPM_API_KEY` is configured.
- Last.fm top tags for genre and mood signals when `LASTFM_API_KEY` is configured.
- Local reference sets for DJ-style energy arcs, genre flow, and transition patterns.

Results are still estimates. BPM, key, and genre data should be reviewed before serious DJ use.

## Current Status

Mixory is an MVP. It does not require Spotify login and does not directly read private Spotify or Apple Music playlists. Users export or paste their tracklists first, then Mixory analyzes the text data.

The backend currently keeps placeholders for future Songstats or Beatport-style enrichment. Those layers can make DJ-specific metadata more reliable later.
