# Changelog

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
