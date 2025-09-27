There are five easy steps to download the large data from Google Drive to your local directory or external hard drive
 #### 1.1) Install the rclone
```brew install rclone```

#### 1.2) Create a Google Drive remote named "gdrive" 
```rclone config create gdrive drive scope=drive.readonly```

#### 2) connect to Google Drive (opens a browser; approve)
```rclone config reconnect gdrive:```

#### 3) Confirm the remote exists
```rclone listremotes   # should show: gdrive:```

#### 4) Make your directory (if you have one, then ignore this step and move to the 5th step) 
```mkdir -p "directory"```

#### 5) Copy the Google Drive link, e.g.,(ID: 10ofdgdfgdfgsurwSFTgiLdfgdfgr) and transfer data to your drive
```
rclone copy --progress \
  --drive-root-folder-id **mention ID here** \
  gdrive: "~/path/to/your/directory/"

