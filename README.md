# 🎵 PlaylistBridge

Import YouTube playlists directly into Spotify, automatically — no installation needed, no backend, runs entirely in the browser.

## How it works

1. Paste a YouTube playlist link
2. The app fetches the tracks via YouTube Data API v3
3. Log in to Spotify via OAuth 2.0 (PKCE)
4. The app searches for each track on Spotify and creates the playlist automatically

## Requirements

You'll need two free API keys:

**YouTube Data API v3**
- Go to [Google Cloud Console](https://console.cloud.google.com)
- Enable the YouTube Data API v3
- Create an API key

**Spotify Web API**
- Go to [Spotify for Developers](https://developer.spotify.com/dashboard)
- Create a new app
- Under Settings, check **Web API** in "Which API/SDKs are you planning to use?"
- Add `http://127.0.0.1:5500/yt-to-spotify.html` as a Redirect URI
- Copy the Client ID
- Under User Management, add your Spotify account email as an authorized user

## Usage

1. Open `yt-to-spotify.html` in the browser (recommended: via Live Server in VS Code on port 5500)
2. Enter your API keys and click **Save configuration**
3. Click **Sign in with Spotify** and authorize the app
4. Paste your YouTube playlist URL and click **Analyze playlist**
5. Click **Create on Spotify**

## Notes

- API keys are saved only in your browser's `localStorage` — nothing is sent to external servers
- The app runs in Spotify's development mode, so it only works for accounts registered under User Management (up to 5 users)
- Tracks not found on Spotify will be marked as "not found" and skipped
- Matching is done by channel name + video title, with a title-only fallback

## Stack

Pure HTML + CSS + JavaScript — no dependencies, no build step.


built with AI assistance from [Claude](https://claude.ai) by Anthropic
