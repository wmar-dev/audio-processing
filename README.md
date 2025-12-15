# Audio Processing

Convert flac to mp3 (~190kbps variable bit rate).
```bash
for f in *.flac; do ffmpeg -i "$f" -acodec libmp3lame -q:a 2 "${f%.flac}.mp3"; done
```

Convert flac to mp3 (~190kbps variable bit rate) including subdirectories.
```bash
find . -name "*.flac" -exec sh -c 'ffmpeg -i "$1" -acodec libmp3lame -q:a 2 "${1%.flac}.m4a"' _ {} \;
```

Convert flac to alac (Apple Lossless Audio Codec).
```bash
for f in *.flac; do ffmpeg -i "$f" -acodec alac "${f%.flac}.m4a"; done
```

## References
- https://trac.ffmpeg.org/wiki/Encode/MP3