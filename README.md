# lucky-render-upload-log

This library is used as a nexrender action to upload the render worker log file to S3. 
Unfortunately it's not suitable for public use, but you're welcome to fork and create your own version.

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
The module will upload the logfile to the supplied key and S3 Bucket