# Amazon S3

### List

    aws s3 ls                                                            # list buckets
    aws s3 ls s3://bucket/                                               # list objects of a bucket
    aws s3 ls s3://bucket --recursive --human-readable --summarize

Copy

  Copies a local file or S3 object to another location locally or in S3

    aws s3 cp file.txt s3://bucket/folder/file.txt                       # copy a single file and create folder if not exist
    aws s3 cp folder s3://bucket/folder --recursive
    aws s3 cp s3://bucket/object .                                       # copy a single object to local
    aws s3 cp s3://bucket . --recursive                                  # recursively copy all objects in a bucket to local

Delete

    aws s3 rm s3://bucket/test.txt                                      # delete object 'test.txt'
    aws s3 rm s3://bucket --recursive                                   # delete all objects in bucket

Create Bucket

    aws s3 mb s3://new-bucket

  Folders an not be created explicetly; they are implicetly created when copying files

Delete Bucket

    aws s3 rb s3://bucket
    aws s3 rb s3://bucket --force                                       # remove all objects in bucket, then remove bucket itself

Synchronize

  Recursively copy new and updated files from source directory to destination.
  Only creates folders in destination if they contain files.

    aws s3 sync . s3://bucket
    aws s3 sync . s3://thomd --dryrun --exclude "\*.git/*"
