## Encoding h265 / hevc 
`ffmpeg -hwaccel cuvid -i './input.mp4' -c:v nvenc_hevc -crf 8 'nv_out.mp4'`

This works with the out-of-the-box ffmpeg Windows binaries, assuming you have a compatible nvidia gpu + drivers

Be warned: Nvidias nvenc_hevc encoder does not support modifying the resolution (and probably more), so output res will == input res 

-crf can be adjusted up or down to increase/decrease quality: Lower value is less compress / higher quality. Range is between 0-52 and the default is ~23
