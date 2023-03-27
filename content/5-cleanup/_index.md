---
title : "Cleanup"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
1. Empty S3 bucket
- Open the [S3 console](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-2)
- Select **fcjdmsstore...-dev** bucket
- Click **Empty**
- Enter **permanently delete** and click **Empty**

2. Run the below command.
```
amplify delete
```