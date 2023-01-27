# DVC_DEMO
DATA VERSION CONTROL

## Steps

Create a virtual env ,install dvc and clone the git repository to be versioned.

```
conda create --name dvc python=3.8.2 -y 
pip install dvc

```

Then create your branch in Git for each version.

```git checkout -b "V1.0"```

Now you can initiate the dvc by using the below command , then you can find a .dvc folder in your repository and by default dvc stores the analytics of the model, so we can set it to false.

```
dvc init
dvc config core.analytics false

```

In dvc , you need to have remote storage for storing large file , It can be Googledrive , S3 bucket etc .Here, we use the local storage. PATH is the path of the remote storage folder in your computer.

```dvc remote add -d remote_storage PATH```

To add a folder in the tracking list of DVC ( Data folder).

```dvc add PATH```

Now your data is copied to the cache and a .dvc file will be created in place of the csv file. eg: Train.csv -> Train.dvc . In each step after add folder to dvc ensure to add in git and commit them to github.

```git add --all
git commit -m" First Commit " ```

Then push the cache to remote in dvc and also in github using new branch as default.

```dvc push
git push --set-upstream origin BRANCH NAME
```
If you want to extract the data in another setup, Use the following commands.

```
dvc checkout
dvc fetch

```


[Refe]( https://github.com/eswaraprasad001/data-version-control)

