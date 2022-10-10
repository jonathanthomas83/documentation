# ffmpeg to convert to 16 bit 44.1kHz FLAC
```
ffmpeg -i "03 Can I Play With Madness.flac" -sample_fmt s16 -ar 44100 "03 Can I Play With Madness-cd.flac"
```
or
```
ffmpeg -i [source-file] -sample_fmt s16 -ar 44100 [destination-flac]
```

From: [ffmpeg FLAC 24 bit 96khz to 16 bit 48khz - https://stackoverflow.com/questions/41420391/ffmpeg-flac-24-bit-96khz-to-16-bit-48khz](https://stackoverflow.com/questions/41420391/ffmpeg-flac-24-bit-96khz-to-16-bit-48khz)

# Convert multiple files within a directory

`cd` into directory

```
for i in *.flac; do ffmpeg -i "$i" -sample_fmt s16 -ar 44100 "cd/${i%.*}.flac"; done
```

From: [How do you convert an entire directory with ffmpeg? - https://stackoverflow.com/questions/5784661/how-do-you-convert-an-entire-directory-with-ffmpeg](https://stackoverflow.com/questions/5784661/how-do-you-convert-an-entire-directory-with-ffmpeg)