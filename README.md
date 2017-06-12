# YouTubeDrive

**YouTubeDrive** is a Wolfram Language (aka *Mathematica*) package that encodes/decodes arbitrary data to/from simple RGB videos which are automatically uploaded to/downloaded from YouTube. Since YouTube imposes no limits on the total number or of videos users can upload, this provides an effectively infinite but extremely slow form of file storage.

**YouTubeDrive** depends externally on [FFmpeg](https://ffmpeg.org/), [youtube-upload](https://github.com/tokland/youtube-upload), and [youtube-dl](https://rg3.github.io/youtube-dl/). These programs must be downloaded and installed separately, and prior to first use, **YouTubeDrive** must be configured with their install locations. See below for details.

YouTubeDrive is a silly proof-of-concept, and I do not endorse its high-volume use.

## Installation

 * Install [FFmpeg](https://ffmpeg.org/), [youtube-upload](https://github.com/tokland/youtube-upload), and [youtube-dl](https://rg3.github.io/youtube-dl/) as your operating system dictates.
 * Find an arbitrary test video, say `test.mp4`, and run `youtube-upload --title="Test Video" test.mp4`. Follow the displayed instructions to create an OAuth token for your YouTube account. This will be the YouTube account used for all **YouTubeDrive** uploads.
 * Download and open `YouTubeDrive.wl` from this repository.
 * In lines 74-76, enter the install locations of the [FFmpeg](https://ffmpeg.org/), [youtube-upload](https://github.com/tokland/youtube-upload), and [youtube-dl](https://rg3.github.io/youtube-dl/) executables. Make sure to use proper string escape sequences (in particular, backslashes `\` need to be escaped as double-backslashes `\\` in Windows paths).
    ```
    74 | FFmpegExecutablePath = "FFMPEG_PATH_HERE";
    75 | YouTubeUploadExecutablePath = "YOUTUBE-UPLOAD_PATH_HERE";
    76 | YouTubeDLExecutablePath = "YOUTUBE-DL_PATH_HERE";
    ```
   For example, I use the following install locations on my system (Windows 10):
    ```
    74 | FFmpegExecutablePath = "C:\\Games\\MiscExes\\ffmpeg.exe";
    75 | YouTubeUploadExecutablePath = Sequence["python",
    76 |   "C:\\Users\\dzhan\\AppData\\Local\\Programs\\" <>
    77 |       "Python\\Python35\\Scripts\\youtube-upload.py"];
    78 | YouTubeDLExecutablePath = "C:\\Games\\MiscExes\\youtube-dl.exe";
    ```
   Note the use of `Sequence[]` to call `python youtube-upload.py` above.
 * After making the above edits, open `YouTubeDrive.wl` with *Mathematica*. Then, open the **File ⇨ Install...** dialog, and select the following options:
    - Type of Item to Install: **Package**
    - Source: **YouTubeDrive.wl**
    - Install Name: **YouTubeDrive** (no `.wl` suffix)
   
   Choose installation for all users or the current user only, according to your preference, and click **OK**.
