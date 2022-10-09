# ffmpeg to convert to 16 bit 44.1kHz FLAC
```
ffmpeg -i "03 Can I Play With Madness.flac" -sample_fmt s16 -ar 44100 "03 Can I Play With Madness-cd.flac"
```
or
```
ffmpeg -i [source-file] -sample_fmt s16 -ar 44100 [destination-flac]
```

From: [ffmpeg FLAC 24 bit 96khz to 16 bit 48khz - https://stackoverflow.com/questions/41420391/ffmpeg-flac-24-bit-96khz-to-16-bit-48khz](https://stackoverflow.com/questions/41420391/ffmpeg-flac-24-bit-96khz-to-16-bit-48khz)