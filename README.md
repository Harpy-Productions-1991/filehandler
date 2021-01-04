秘書ちゃん

Hisho-chan

handles opening your files for you from the comand line
you call hisho "path to file" or "name of the file" if already in the directory the file is in.
this will open the file with its proper editor or viewer whattever it is.
this can also be used as a file handler by programs like nnn. it can call this program in order to open files by setting NNN_OPENER=hisho

very easy and customizable terminal file handler

it uses 3 things

# 1 environment variables
EDITOR for text files READER for pdfs, epups, etc. BROWSER for web links, MUSIC_PLAYER for music and VIDEO_PLAYER for playing video
# 2 extension variables
in hisho-chan file itself named ext_* to identify each file type by extension. ext_video might be "mp4 avi" and so on, any extension that is used on video files
# 3 descriptions variables
also in hisho-chan file named desc_* using strings you can get by using the shell command file "file name", the description might contain strings that identify what kind of file you are trying to open similar to extensions
but since it is possible to have files without extension, and wrong file extensions, we check for both and file description takes priority

this way it is easy to extend the pogram by adding more file descriptions and extension to the variables
if you see ext_video="avi mkv" and you want to open a video with another extension all you have to do is add the extension to that variable like this
ext_video"avi mkv mp4" now it will handles mp4 with the same video player

if file commands does not find the file you are trying to open, it will assume it is an web link and try to open it in BROWSER
