# Features:
- File rename with Mirror/Leech/Clone/Torrent/Mega
- Auto Mute users on wrong command
- Dyno Sleep
- Area2/Qbit Torrent Seed with sepcific retio and time
- Select Files before and after start download
- Telegram Premium 4GB Leech
- Heroku Dyno Status
- Leech Size Limit
- Leech-Log, Mirror-Log, Bot-PM
- Force Sub to channel
- AppDrive & GdToT Support
- qBittorrent
- Select files from Torrent before downloading using qbittorrent
- Leech (splitting, thumbnail for each user, setting as document or as media for each user)
- Size limiting for Torrent/Direct, Zip/Unzip, Mega and Clone
- Stop duplicates for all tasks except yt-dlp tasks
- Zip/Unzip G-Drive links
- Counting files/folders from Google Drive link
- View Link button, extra button to open file index link in broswer instead of direct download
- Status Pages for unlimited tasks
- Clone status
- Search in multiple Drive folder/TeamDrive
- Recursive Search (only with `root` or TeamDrive ID, folder ids will be listed with non-recursive method)
- Multi-TD list by token.pickle if exists
- Extract rar, zip and 7z splits with or without password
- Zip file/folder with or without password
- Use Token.pickle if file not found with Service Account for all Gdrive functions
- Random Service Account at startup
- Mirror/Leech/Watch/Clone/Count/Del by reply
- YT-DLP quality buttons
- Search on torrents with Torrent Search API or with variable plugins using qBittorrent search engine
- Docker image support for linux `amd64, arm64, arm/v7, arm/v6, s390x, arm64/v8` (**Note**: Use `412314/mltb:arm64` for `arm64/v8` or oracle)
- Update bot at startup and with restart command using `UPSTREAM_REPO`
- Qbittorrent seed until reaching specific ratio or time
- Rss feed and filter. Based on this repository [rss-chan](https://github.com/hyPnOtICDo0g/rss-chan)
- Save leech settings including thumbnails in database
- Mirror/Leech/Clone multi links/files with one command
- Extenstion Filter for uploading/cloning files
- Incomplete task notifier to get incomplete task messages after restart, works with database.
- Many bugs have been fixed
- Mirror direct download links, Torrent, and Telegram files to Google Drive
- Mirror Mega.nz links to Google Drive
- Copy files from someone's Drive to your Drive (Using Autorclone)
- Download/Upload progress, Speeds and ETAs
- Mirror all yt-dlp supported links
- Docker support
- Uploading to Team Drive
- Index Link support
- Service Account support
- Delete files from Drive
- Shortener support
- Multiple Trackers support
- Shell and Executor
- Add sudo users
- Custom Filename* (Only for direct links, Telegram files and yt-dlp. Not for Mega links, Gdrive links or Torrents)
- Extract password protected files
- Extract these filetypes and uploads to Google Drive
  > ZIP, RAR, TAR, 7z, ISO, WIM, CAB, GZIP, BZIP2, APM, ARJ, CHM, CPIO, CramFS, DEB, DMG, FAT, HFS, LZH, LZMA, LZMA2, MBR, MSI, MSLZ, NSIS, NTFS, RPM, SquashFS, UDF, VHD, XAR, Z, TAR.XZ

- Direct links Supported:
  >letsupload.io, hxfile.co, anonfiles.com, bayfiles.com, antfiles, fembed.com, fembed.net, femax20.com, layarkacaxxi.icu, fcdn.stream, sbplay.org, naniplay.com, naniplay.nanime.in, naniplay.nanime.biz, sbembed.com, streamtape.com, streamsb.net, feurl.com, pixeldrain.com, racaty.net, 1fichier.com, 1drv.ms (Only works for file not folder or business account), uptobox.com (Uptobox account must be premium) and solidfiles.com


## Deploying on Github Actions

**Required Variables(Add in Settings -> Secrets -> Actions -> Actions secrets -> New repository secret):**

- `GIT_NAME` : Add your Github Username.
- `GIT_EMAIL` : Add your Github Email.
- `GIT_TOKEN` : Enter your `Personal Access Github Token` and Give All Permission, it will use your account to Run the Loop Server . [Click Here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#creating-a-token) to Generate.
- `BOT_REPO` : Put your Forked or this Repo link after removing **_https://_** from Beginning of the URL.
- `CONFIG_FILE_URL` : Gist URL contains All Required Vars for Z-Mirror, Fill it and Remove Commit ID.

**NOTE**: **GitHub Free** accounts has **2000** minutes of action runtime and **GitHub Pro** accounts has **3000** minutes of action runtime.

------

## Bot commands to be set in [@BotFather](https://t.me/BotFather)

```
start - Auth Stats
mirror - Mirror
zipmirror - Mirror and upload as zip
unzipmirror - Mirror and extract files
qbmirror - Mirror torrent using qBittorrent
qbzipmirror - Mirror torrent and upload as zip using qb
qbunzipmirror - Mirror torrent and extract files using qb
leech - Leech
zipleech - Leech and upload as zip
unzipleech - Leech and extract files
qbleech - Leech torrent using qBittorrent
qbzipleech - Leech torrent and upload as zip using qb
qbunzipleech - Leech torrent and extract using qb
clone - Copy file/folder to Drive
count - Count file/folder of Drive
watch - Mirror yt-dlp supported link
zipwatch - Mirror yt-dlp supported link as zip
leechwatch - Leech through yt-dlp supported link
leechzipwatch - Leech yt-dlp support link as zip
leechset - Leech settings
setthumb - Set thumbnail
status - Get Mirror Status message
rsslist - List all subscribed rss feed info
rssget - Get specific No. of links from specific rss feed
rsssub - Subscribe new rss feed
rssunsub - Unsubscribe rss feed by title
rssset - Rss Settings
list - Search files in Drive
search - Search for torrents with API
cancel - Cancel a task
cancelall - Cancel all tasks
del - Delete file/folder from Drive
log - Get the Bot Log
shell - Run commands in Shell
restart - Restart the Bot
stats - Bot Usage Stats
ping - Ping the Bot
help - All cmds with description
```
------

## UPSTREAM REPO (Recommended)

- `UPSTREAM_REPO` variable can be used for edit/add any file in repository.
- You can add private/public repository link to grab/overwrite all files from it.
- You can skip adding the privates files like token.pickle or accounts folder before deploying, also no need to add variables direct links except **config.env**, simply fill `UPSTREAM_REPO` private one in case you want to grab all files including private files.
- If you added private files while deploying and you have added private `UPSTREAM_REPO` and your private files in this private repository, so your private files will be overwritten from this repository. Also if you are using URL variables like `TOKEN_PICKLE_URL` then all files from those variables will override the private files that added before deploying or from private `UPSTREAM_REPO`.
- If you filled `UPSTREAM_REPO` with the official repository link then be carefull incase any change in requirements.txt your bot will not start after restart. In this case you need to deploy again with updated code to install the new requirements or simply by changing the `UPSTREAM_REPO` to you fork link with that old updates or make it empty if deployed master branch.
- In case you you filled `UPSTREAM_REPO` with your fork link be carefull also if you fetched the commits from the official repository.
- The changes in your `UPSTREAM_REPO` will take affect only after restart.
- `UPSTREAM_BRANCH` don't ever fill heroku here.


-----

## Gdtot Cookies
To Clone or Leech gdtot link follow these steps:
1. Login/Register to [gdtot](https://new.gdtot.top).
2. Copy this script and paste it in browser address bar.
   - **Note**: After pasting it check at the beginning of the script in broswer address bar if `javascript:` exists or not, if not so write it as shown below.
   ```javascript
   javascript:(function () {
    const input = document.createElement('input');
    COOKIE = JSON.parse(JSON.stringify({cookie : document.cookie}));
    input.value = COOKIE['cookie'].split('crypt=')[1];
    document.body.appendChild(input);
    input.focus();
    input.select();
    var result = document.execCommand('copy');
    document.body.removeChild(input);
     if(result)
       alert('Crypt copied to clipboard');
     else
       prompt('Failed to copy Crypt. Manually copy below Crypt\n\n', input.value);
   })();
   ```
   - After pressing enter your browser will prompt a alert.
3. Now you'll get Crypt value in your clipboard
   ```
   NGxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxWdSVT0%3D
   ```
4. From this you have to paste value for **CRYPT** in config.env file.

-----
