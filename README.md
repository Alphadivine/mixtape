# Mixtape

A small, private place for a group of friends to share songs with each other, react and rate them, and build a shared Spotify playlist. Sibling to WatchLog (movies/shows) and Party Up (games).

## Features

- **Share a song**: search by name/artist, or paste a Spotify, Apple Music or YouTube link. Artwork, album, year and a 30-second preview are filled in automatically.
- **Works with any service**: every song gets Spotify, Apple Music and YouTube Music buttons, so friends on different apps can all listen.
- **Notes**: add a "why you should listen" message when you share.
- **Reactions & ratings**: 🔥 ❤️ 😮 😂 💤 reactions plus your own 1–5 star rating; cards show the group average.
- **Mark listened**: track what you've heard; "New to me" filter shows only what you haven't.
- **Comments**: a thread on every song.
- **Send to a person**: recommend a song straight to specific friends. It lands in their **Inbox** with a badge until they listen.
- **Group playlist**: one tap opens the shared Spotify playlist. **+ Playlist** adds a song instantly if you've connected Spotify, or queues it so someone connected can add the whole queue at once.
- **Filters & search**: All, New to me, Top rated, Playlist, Shared by me.
- **Installable**: add to your phone's home screen like an app.

## Tech

- Single-page app on GitHub Pages (no build step).
- Firebase Auth (Google) + Cloud Firestore for songs, comments, people and group settings.
- Song lookup: iTunes Search API. Cross-service links: song.link (Odesli) API.
- Spotify Web API with Authorization Code + PKCE in the browser (no server, no client secret).

## Setup

See `Docs/Setup guide.md` in the app bundle.

## Data

| Collection | What's in it |
| --- | --- |
| `songs` | Song info, links, who shared it, note, reactions, ratings, listened, sends, playlist status |
| `songs/{id}/comments` | Comment thread |
| `users` | Name and photo of everyone who has signed in |
| `settings/group` | Playlist link and Spotify Client ID |

Spotify sign-in tokens stay on each person's device (browser storage) and are never written to Firestore.

---
Last updated: 2026-10-08
