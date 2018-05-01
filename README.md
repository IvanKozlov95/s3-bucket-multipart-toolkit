# s3-bucket-version

S3 Bucket Version made easy

## Install

```bash
$ npm i s3-bucket-version --save
```

## Configure

```js
const AWSBucket = require('s3-bucket-version');

const bucket = new AWSBucket({
  accessKeyId: 'your-access-key-here',
  secretAccessKey: 'your-secret-here',
  region: 'us-east-1',
  bucketName: 'my-bucket'
});

```

## Usage


### List all buckets

Get All buckets for this account

```js
bucket.getAllBuckets().then(function(res) {
  /* Buckets => res.Buckets */
}).catch(function(err) {
  /* err */
});

/*
Result:
{
  Buckets:
   [ { Name: 'my-bucket',
       CreationDate: 2018-03-19T17:49:05.000Z } ],
  Owner:
   { DisplayName: 'cris',
     ID: '...' }
}
*/

```

### Get Upload URL

Get upload URL

```js
bucket.getUploadUrl({
  ContentType: 'application/javascript',
  Key: 'your-dir/test.js'
}).then(function(res){
  /* Signed URL => res.signedUrl */
}).catch(function(err){
  /* err */
});

/*
Result:
{
  signedUrl: 'https://your-bucket.s3.amazonaws.com/your-dir/test.js?AWSAccessKeyId=...'
}
*/
```

### List files

```js
```
