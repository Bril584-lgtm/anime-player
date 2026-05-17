# Anime Player

A minimal video player page for sharing anime episodes on Discord. When someone clicks the link, they see only the video — nothing else.

**Live URL:** https://bril584-lgtm.github.io/anime-player/

---

## How to Use

### Step 1 — Get a stream URL

Open **Git Bash** and run:

```bash
ani-cli --dub -e 1 -q 1080 -p debug
```

- When prompted, type the anime name (e.g. `Mato Seihei` for Chained Soldier)
- Select the correct season from the list
- Copy the URL printed under **"Selected link:"**

To watch locally instead of getting the URL, drop `-p debug`:

```bash
ani-cli --dub -e 1 -q 1080
```

---

### Step 2 — Build the shareable link

```
https://bril584-lgtm.github.io/anime-player/?title=TITLE&url=VIDEO_URL
```

| Parameter | Required | Description |
|-----------|----------|-------------|
| `url`     | Yes      | Direct `.mp4` or `.m3u8` stream URL |
| `title`   | No       | Sets the page title (shows in Discord embed) |

**Example:**
```
https://bril584-lgtm.github.io/anime-player/?title=Chained+Soldier+Ep+1+Dub&url=https://example.com/video.mp4
```

---

### Step 3 — Share on Discord

Paste the full link into Discord. Anyone who clicks it lands on a plain black page with just the video playing — no ads, no UI, nothing else.

---

## Notes

- **Stream URLs expire** — AllAnime URLs last only a few hours. For a permanent link, download the episode first and upload to a file host like [litterbox.catbox.moe](https://litterbox.catbox.moe) (free, up to 1GB, 72h).
- **Download an episode** with ani-cli using the `-d` flag:
  ```bash
  ani-cli --dub -e 1 -q 1080 -d
  ```
- Supports both `.mp4` (native) and `.m3u8` HLS streams (via HLS.js).

---

## Tools Used

| Tool | Purpose |
|------|---------|
| [ani-cli](https://github.com/pystardust/ani-cli) | Find and stream anime from the terminal |
| [mpv](https://mpv.io) | Local video playback |
| [yt-dlp](https://github.com/yt-dlp/yt-dlp) | Download video streams |
| [ffmpeg](https://ffmpeg.org) | Video processing |
