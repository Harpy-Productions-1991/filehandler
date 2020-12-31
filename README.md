Filehandler

handles opening your files, duh

very easy and customizable terminal file handler

it uses 3 things, environment variables to set your file openers
# 1
EDITOR for text files READER for pdfs, epups, etc. BROWSER for web links, MUSIC_PLAYER for music and VIDEO_PLAYER for playing video
# 2
variables in filehandler itself named ext_* to identify each file type by extension. ext_video might be "mp4 avi" and so on, any extension that is used on video files
# 3
more variables in filehandler named mime_* using strings you can get by using the shell command file "path to file", the description might contain strings similar of these in extension
but since it is possible to have files without extension we check for both

it first identify the description with the file command and the extension
then it tries to match the description with words from the mime_* var if it matches it uses the opener for that file type, if it fails it them uses the extension. this way we avoid being
tricked by wrong extensions

this way it is easy to extend the pogram by adding more file descriptions and extension to the variables
if you see ext_video="avi mkv" and you try to open a video with another extension all you have to do is add the extension to that variable like this
ext_video"avi mkv mp4" now it will handles mp4 with the same video player
if file commands does not find the file you are trying to open, it will assume it is an web link and try to open it in BROWSER
