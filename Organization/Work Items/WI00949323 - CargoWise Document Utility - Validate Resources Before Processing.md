
Product: [[What is CargoWise Document Utility]]
The work item is fundamentally about testing that resources exist before initializing the document utility. E.g. S3 buckets exist, Databases exist, folders/zip archives exist.


## Current Problem
The spec for the document utility work item says that we should check "if a bucket exists". It is not super clear what this means, do we just check if the bucket exists since they are globally unique or do we check if we can access objects within it with a given key? Especially because AWS S3 allows for fine grained access that allows some keys to be able to access some objects.

## Solution
Just leave as is (checking if the bucket exists).
Left comment in WI

```
M22 24-Feb-26 14:04 GMT+11:00:

  

response to "PTW 12-Feb-26 18:23 GMT+11:00: Hi Mukund, please check UAT edoc. I rebuilt on DAT and attempted the 1st test as specified in your instructions. I added fake S3 creds to my local test db via CW, then attempted the tool but it doesn't seem to give error 101. Can you see if I'm doing something wrong, or if requires iteration?"

  

Hey patrick apologies for holding this work item for so long. I investigated the error briefly and found the reason for the s3 bucket existence check succeeding when you tried to initialize a connection to a bucket called "garbage" was due to s3 buckets being globally unique and technically accessible from any valid access key and secret key, so you were able to successfully initialize a connection to this bucket. So this was expected behaviour.

  

As for whether or not we want to modify this behaviour, I don't think it matters so much. While it is true at wisetech we segregate 1 bucket to 1 customer using naming convention "wced-<region>-<awsAccountId>-<systemCode>-001-<role>", to query for objects within a bucket is too much work since access credentials may not even have permission to do that. In short, I don't want to make any further changes.

  

If you could repeat the functional test but using a bucket name that definitely does not exist such as "patricksbucketthatsurelydoesnotexist", the test should pass. Any questions lmk, happy to discuss furhter.
```