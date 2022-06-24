# ytdlbot

1. fast download and upload.
2. ads free
3. support progress bar
4. audio conversion
5. playlist support
6. VIP support
7. support different video resolutions
8. support sending as file or streaming as video
9. supports celery worker distribution - faster than before.
10. subscriptions to YouTube Channels
11. cache mechanism - download once for the same video.


## Run natively on your machine

 install ffmpeg and Python 3.6+
 clone code
 `pip3 install -r requirements.txt`
  set environment variables `TOKEN`, `APP_ID` and `APP_HASH`, and more if you like.
 `python3 ytdl_bot.py`


you can configure all the following environment variables:

* PYRO_WORKERS: number of workers for pyrogram, default is 100
* WORKERS: workers count for celery
* APP_ID: **REQUIRED**, get it from https://core.telegram.org/
* APP_HASH: **REQUIRED**
* TOKEN: **REQUIRED**
* REDIS: **REQUIRED if you need VIP mode and cache** ⚠️ Don't publish your redis server on the internet. ⚠️

* OWNER: owner username
* QUOTA: quota in bytes
* EX: quota expire time
* MULTIPLY: vip quota comparing to normal quota
* USD2CNY: exchange rate
* VIP: VIP mode, default: disable
* AFD_LINK
* COFFEE_LINK
* COFFEE_TOKEN
* AFD_TOKEN
* AFD_USER_ID

* AUTHORIZED_USER: users that could use this bot, user_id, separated with `,`
* REQUIRED_MEMBERSHIP: group or channel username, user must join this group to use the bot. Could be use with
  above `AUTHORIZED_USER`

* ENABLE_CELERY: Distribution mode, default: disable. You'll can setup workers in different locations.
* MYSQL_HOST: you'll have to setup MySQL if you enable VIP mode
* MYSQL_USER
* MYSQL_PASS
* GOOGLE_API_KEY: YouTube API key, required for YouTube video subscription.
* AUDIO_FORMAT: audio format, default is m4a. You can set to any known and supported format for ffmpeg. For
  example,`mp3`, `flac`, etc. ⚠️ m4a is the fastest. Other formats may affect performance.
* ARCHIVE_ID: group or channel id/username. All downloads will send to this group first and then forward to end user.
  **Inline button will be lost during the forwarding.**


**⚠️ Bear in mind don't publish redis directly on the internet! You can use WireGuard to wrap it up.**

# Command

```cmd
start - Let's start
about - What's this bot?
ping - Bot running status
help - Help
ytdl - Download video in group
vip - Join VIP
terms - View Terms of Service
settings - Set your preference
direct - Download file directly
sub - Subscribe to YouTube Channel
unsub - Unsubscribe from YouTube Channel
sub_count - Check subscription status, owner only.
uncache - Delete cache for this link
```

# License

Apache License 2.0
