# dvc_tutorial
data version control tutorial


# Do it

0. first, you should make a git repository. and then clone it to your local computer

1. install
```shell
pip install dvc
```

2. initialize dvc project
```
dvc init
```

3. add remote repository
```
pip install dvc_gdrive
dvc remote list
dvc remote add -d mygdrive gdrive://<folderID>
```

4. add first version of data
```
dvc get https://github.com/iterative/dataset-registry tutorials/versioning/data.zip
unzip data.zip & rm -f data.zip
dvc add data/
dvc push
```

```
git commit -m "ADD first version of data/"
git tag -a "v1.0" -m "data v1.0 1000 images"
git push
```

5. add new version of data
```
dvc get https://github.com/iterative/dataset-registry tutorials/versioning/new-labels.zip
unzip new-labels.zip & rm -f new-labels.zip
dvc add data/

dvc diff
git diff data.dvc
git commit -am "New version of data/ with more training images"
git tag -a "v2.0" -m "data v2.0, 2000 images"
dvc push
```
