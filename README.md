There are five easy steps to download the large data from google drive to your local directory or external hard drive
 #### 1.1) install the rclone
```brew install rclone```

#### 1.2) Create a Google Drive remote named "gdrive" 
```rclone config create gdrive drive scope=drive.readonly```

#### 2) connect to googel drive (opens a browser; approve)
```rclone config reconnect gdrive:```

#### 3) confirm the remote exists
```rclone listremotes   # should show: gdrive:```

#### 4) Make your directory (if have then ignore this step and move to 5th step) 
```mkdir -p "/Volumes/Toshiba/kaust_data"```

#### 5) Copy the google drive link, e.,g.,(ID: 10ofdgdfgdfgsurwSFTgiLdfgdfgr) and transfer data to your drive
```rclone copy --progress \
  --drive-root-folder-id **mention ID here** \
  gdrive: "~/path/to/your/directory/"```
