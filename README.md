# yt_dlp_wrapper_flask

![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=ffdd54)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![yt-dlp](https://img.shields.io/badge/yt--dlp-FF0000?style=flat&logo=youtube&logoColor=white)

A tiny Flask HTTP wrapper around [`yt-dlp`](https://github.com/yt-dlp/yt-dlp) that **extracts a specific time range from a YouTube video or livestream** as a downloadable clip. Used as a microservice by my other projects so the heavy yt-dlp work lives behind one simple URL.

## Endpoint

```
GET /download/<video-id>/<start-time>/<end-time>
```

- `video-id` — the YouTube video ID, e.g. `https://www.youtube.com/watch?v=nWed2eTY7_Q` → `nWed2eTY7_Q`
- `start-time` / `end-time` — seconds (int or float).

Returns the trimmed segment for that time range.

## Run

```bash
pip install -r requirements.txt
python app.py
```

> Requires FFmpeg (yt-dlp uses it to trim/merge). Install scripts (`install.sh`, `start.sh`) are included to set things up on a server.
