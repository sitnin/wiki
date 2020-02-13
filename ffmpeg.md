ffmpeg -i Sample.avi -vn -ar 44100 -ac 2 -ab 192k -f mp3 Sample.mp3

ffmpeg -i input-video.avi -vn -acodec copy output-audio.aac


To encode a high quality MP3 from an AVI best using -q:a for variable bit rate.

ffmpeg -i sample.avi -q:a 0 -map a sample.mp3

If you want to extract a portion of audio from a video use the -ss option to specify the starting timestamp, and the -t option to specify the encoding duration, eg from 3 minutes and 5 seconds in for 45 seconds

ffmpeg -i sample.avi -ss 00:03:05 -t 00:00:45.0 -q:a 0 -map a sample.mp3

The timestamps need to be in HH:MM:SS.xxx format or in seconds.
If you don't specify the -t option it will go to the end.

ffmpeg -formats
ffmpeg -codecs




ffmpeg -i movie.mp4 -ss 00:00:03 -t 00:00:08 -async 1 cut.mp4


ffmpeg -i input.mp4 -ss 00:01:00 -to 00:02:00 -c copy output.mp4

http://blog.georgechalhoub.com/2017/03/trimming-videos-via-ffmpeg.html



slowdown video 4x

```
ffmpeg -i input.mkv -r 16 -filter:v "setpts=0.25*PTS" output.mkv
```

speedup audio 2x

```
ffmpeg -i input.mkv -filter:a "atempo=2.0" -vn output.mkv
```

