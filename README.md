## Prerequisites
Should we install git-lfs first?
```
git lfs install
git lfs track "*.pdf"
git add .gitattributes
git commit -m "Configure git lfs"
```


```
uv tool install 'git-remote-s3@https://github.com/SashaOv/git-remote-s3/archive/refs/heads/feature/lfs-only.zip'
git-lfs-s3 install
git config --file .lfsconfig remote.origin.lfsurl s3://my-git-bucket/lfs-repo
git config --add lfs.customtransfer.git-lfs-s3.path git-lfs-s3
git config --add lfs.standalonetransferagent git-lfs-s3
```

## Localstack

```
export AWS_ENDPOINT_URL=http://localhost:4566
export AWS_ACCESS_KEY_ID="AWS_ACCESS_KEY_ID"
export AWS_SECRET_ACCESS_KEY="AWS_SECRET_ACCESS_KEY"
```
