# Changelog

## 2026-10 — Player, crew stats, mood tags, playlist sync, guide & What's New
- Mini player bar above the menu (pause, next, mark listened, lock-screen controls) and "Play all new" / "Play your inbox" to run through unheard previews
- Mood tags: preset + custom tags (up to 4) when sharing or from a song's page; tag filter chips in the feed
- Crew tab: highlights (most shared, best taste, most 🔥, top listener), per-person stats, taste match %, and each person's shares
- Two-way Spotify playlist sync every few minutes plus "Sync with playlist" in Settings: unmarks songs removed in Spotify, marks songs that are in it, and imports songs added straight in Spotify (needs a one-time Reconnect for the new read permission)
- "New since your last visit" divider in the feed
- Undo instead of confirm pop-ups for deleting songs/comments and removing from the playlist
- Android share target: Mixtape appears in Spotify's Share menu once installed
- Slimmer song cards: service icons, listened, comments, send and playlist on one row; rating average moved to the byline
- New ❓ How to use guide (opens once for new users) and ✨ What's New (pops up once per update with what changed since your last visit)
- Firestore rules: anyone can now edit tags and playlistAt (republish rules)

## 2026-10 — Remove songs from the playlist
- New "Remove from playlist" button on songs that are in the group Spotify playlist; anyone connected to Spotify can use it, and the song stays in Mixtape
- Deleting a song you shared now also takes it off the Spotify playlist when you're connected (and warns you if you're not, since it would stay there)

## 2026-10 — Fix Spotify connect
- Fixed: returning from Spotify after tapping Connect Spotify silently failed (the app started before the Spotify code was loaded), so the page just reloaded with no connection
- Settings now reopens after the Spotify round-trip and shows the result in plain words (connected, declined, wrong redirect URI, etc.) instead of a quick toast
- Tapping Connect Spotify with no Client ID saved now opens the Spotify app settings and points you to the Client ID box

## 2026-10 — First release
- Share songs by search or by pasting a Spotify / Apple Music / YouTube link; artwork, album and 30-second preview filled in automatically
- Spotify, Apple Music and YouTube Music buttons on every song (via song.link) so the group can listen on any service
- Reactions, 1–5 star ratings with group average, and "Mark listened"
- Comment threads on every song
- Send a song to specific friends; it shows in their Inbox with an unread badge
- Group Spotify playlist: open it from the header; "+ Playlist" adds instantly for connected Spotify users (PKCE, no server) or queues the song for someone connected to add
- Filters (All, New to me, Top rated, Playlist, Shared by me) and search
- Duplicate check when sharing a song someone already posted
- Google sign-in, Firestore rules, installable PWA
