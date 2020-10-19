# farming-changes-wrt-climate
Prediction of farming changes wrt climatic changes in a region in Switzerland with GitHub actions and DVC pipelining
<br><br> Here an attempt is made to create a continuous verification, integration and deployment system (CI/CD) of models using GitHub containers with the help of DVC pipelining and github actions.
<br><br><br> Note: Here we are just using DVC for creating a pipeline(no use of data versioning here as data is collected from cloud) to be used by github actions every time a pull request is made.
<br><br><br> The steps followed here to create the pipeline and integrate it with github actions are:
  - the required python scripts are added to the folder
  - DVC is initiated using **dvc init**
  - a snapshot is created in GitHub for the current status of the folder using **git commit** and **git push**
  
