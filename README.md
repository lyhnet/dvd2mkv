# dvd2mkv
archiving of dvds




1) MakeMKV move to mkv container (untouched)
2) find sub title srt.. opensubs
3) Sync it by SubtitleEdit and save:find two key frames and set times with 
4) detect crop with ffmpeg Syncronisation -> point sync
    ffmpeg -i input.mp4 -vf "cropdetect=24:16:0" -frames:v 100 -f null -
5) encode with ffmpeg replacing the crop with value from step 4)
ffmpeg -i F1_t00.mkv -i sub.srt -vf "yadif, crop=704:544:10:14" -c:v libsvtav1 -crf 30 -preset 8 -c:a copy  output.mkv
