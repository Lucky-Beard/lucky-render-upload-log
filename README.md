# lucky-render-upload-log

This library is used as a nexrender postrender action to upload the render worker log file to the cloud. 
It utilizes the provider packages of Nexrender and supports the same cloud uploads as the regular nexrender/action-upload

## Usage
Install using npm or yarn
```
npm install lucky-render-upload-log / yarn add lucky-render-upload-log 
```
Usage from the api/client sdk.
```
actions: {
    postrender: [
        {
                "module": "lucky-render-upload-log",
                "provider": "s3",
                "params": {
                    "region": "eu-west-1",
                    "bucket": "bucket-name",
                    "key": "logs",
                    "acl": "private"
                }
            }
    ]
    
}
```

## How it works
The module will upload the logfile to the supplied key and S3 Bucket. 

## Notes
Note that you don't need to supply the file name in the key, it only needs a folder name. The script will append the job log to the key.