# scrub

Go here, scrub: https://pnutus.github.io/scrub2

Only works in Safari at the moment.

## How

I used `ffmpeg` to create scrubbable video. I needed to encode the videos with every frame being a keyframe (or I-frame, in video compression parlance) to make seeking fast enough. For `ffmpeg` that's done by adding `-g 1` to the command line parameters.

Here's a full command that works in Safari:

`ffmpeg -i input.mp4 -g 1 -vcodec libx264 -crf 15 -pix_fmt yuv420p output.mp4`
