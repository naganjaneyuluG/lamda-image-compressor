# Image Resizer Lambda

This Lambda will be invoked when a file is uploaded to a particular bucket. It will fetch the file that was added, resize it, and store the output in a different bucket.
<br>

# Image compression architecture on AWS
## 2 Bucket Image Compression Architecture
![alt text](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fi.ibb.co%2FJ2RFfZL%2Fsystem-architecture.png)

## Single bucket trigger recursive event loop
![alt text](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fi.ibb.co%2F0QjBZhr%2Frecursive-bucket.png)

## Run Locally

Clone the project


Install Dependencies

```bash
# Required options if on mac
npm install --arch=x64 --platform=linux --target=16x sharp
```

## Environment Variables

Remember set the `DEST_BUCKET` in your Lambda's "Configuration" tab. To do this, open your Lambda in the AWS Console, select the "Configuration" tab, then click "Environment variables"

```bash
DEST_BUCKET=s3bucketname
```

## Deployment

```bash
npm run package
```

Running the command above will zip your source code and dependencies. The zip can then be uploaded to your Lambda.
## Supported Image Formats

The following image formats are supported:

- `jpg`
- `jpeg`
- `png`


Ref: https://dev.to/aarongarvey/size-matters-image-compression-with-lambda-and-s3-40bf
