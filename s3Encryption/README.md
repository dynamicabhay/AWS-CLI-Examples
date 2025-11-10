## create a bucket
aws s3 mb s3://encryption-ab

### create a file
echo "hello world" > file.txt

### put object with encryption of KMS
aws s3api put-object \
    --bucket encryption-ab \
    --key myfile \
    --body file.txt \
    --server-side-encryption aws:kms \
    --ssekms-key-id 986c0bdf-d769-4147-8243-f8448f671d8b
