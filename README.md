# Mixtape

A small, private place for a group of friends to share songs with each other, react and rate them, and build a shared Spotify playlist. Sibling to WatchLog (movies/shows) and Party Up (games).

## Features

- **Share a song**: search by name/artist, or paste a Spotify, Apple Music or YouTube link. Artwork, album, year and a 30-second preview are filled in automatically. On Android, once installed, Mixtape also shows up in Spotify's **Share** menu.
- **Works with any service**: every song has Spotify, Apple Music and YouTube Music buttons, so friends on different apps can all listen.
- **Mini player**: previews keep playing in a bar above the menu. **Play all new** (feed) and **Play your inbox** run through everything you haven't heard.
- **Notes & mood tags**: add a "why you should listen" note and tags like #chill or #gym (or your own); filter the feed by tag.
- **Reactions & ratings**: 🔥 ❤️ 😮 😂 💤 reactions plus your own 1–5 star rating; cards show the group average.
- **Mark listened**: track what you've heard; "New to me" shows only what you haven't, and a divider marks what's new since your last visit.
- **Comments**: a thread on every song.
- **Send to a person**: recommend a song straight to specific friends. It lands in their **Inbox** with a badge until they listen.
- **Group playlist**: **+ Playlist** adds a song instantly if you've connected Spotify, or queues it for someone connected. Anyone connected can **Remove from playlist**, and deleting a song you shared takes it off too. Mixtape **syncs both ways** with the Spotify playlist every few minutes.
- **Crew tab**: who shares the most, whose picks rate best, who gets the most 🔥, and your taste match % with each friend.
- **Undo**: deletes and playlist removals show an Undo button instead of a pop-up.
- **How to use** (❓) and **What's New** (✨) built in.
- **Filters & search**: All, New to me, Top rated, Playlist, Shared by me, plus tags.
- **Installable**: add to your phone's home screen like an app.

## Tech

- Releasing an update: bump `APP_VERSION` and add an entry to `WHATS_NEW` in `index.html` so everyone gets the What's New popup.

- Single-page app on GitHub Pages (no build step).
- Firebase Auth (Google) + Cloud Firestore for songs, comments, people and group settings.
- Song lookup: iTunes Search API. Cross-service links: song.link (Odesli) API.
- Spotify Web API with Authorization Code + PKCE in the browser (no server, no client secret).

## Setup

See `Docs/Setup guide.md` in the app bundle.

## Data

| Collection | What's in it |
| --- | --- |
| `songs` | Song info, links, who shared it, note, mood tags, reactions, ratings, listened, sends, playlist status (songs imported from the Spotify playlist have ids starting `sp_`) |
| `songs/{id}/comments` | Comment thread |
| `users` | Name and photo of everyone who has signed in |
| `settings/group` | Playlist link and Spotify Client ID |

Spotify sign-in tokens stay on each person's device (browser storage) and are never written to Firestore.

---
Last updated: 2026-10-09
