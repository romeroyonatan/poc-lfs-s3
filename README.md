## Prerequisites
Install git lfs: https://git-lfs.com/

Configure git lfs
```
git lfs install
git lfs track "*.pdf"
git add .gitattributes
git commit -m "Configure git lfs"
```

Install and configure git-remote-s3
```
uv tool install 'git-remote-s3@https://github.com/SashaOv/git-remote-s3/archive/refs/heads/feature/lfs-only.zip'
git-lfs-s3 install
git config --file .lfsconfig remote.origin.lfsurl s3://my-git-bucket/lfs-repo
git config --add lfs.customtransfer.git-lfs-s3.path git-lfs-s3
git config --add lfs.standalonetransferagent git-lfs-s3
```

## Localstack
Setup a localstack instance for tests
```
export AWS_ENDPOINT_URL=http://localhost:4566
export AWS_ACCESS_KEY_ID="AWS_ACCESS_KEY_ID"
export AWS_SECRET_ACCESS_KEY="AWS_SECRET_ACCESS_KEY"
export AWS_REGION=us-east-1
aws s3 mb s3://my-git-bucket
```

## Push files
```
git add pdfs/
git commit -m "Add pdf"
git push
```
