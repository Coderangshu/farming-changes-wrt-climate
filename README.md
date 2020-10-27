# farming-changes-wrt-climate
Prediction of farming changes wrt climatic changes in a region in Switzerland with GitHub actions and DVC pipelining
<br><br> Here an attempt is made to create a continuous verification, integration and deployment system (CI/CD) of models using GitHub containers with the help of DVC pipelining and github actions.
<br><br><br> Note: Here we are just using DVC for creating a pipeline(no use of data versioning here as data is collected from cloud) to be used by github actions every time a pull request is made.
<br><br><br> The steps followed here to create the pipeline and integrate it with github actions are:
  - the required python scripts are added to the folder
  - DVC is initiated using **dvc init**
  - a snapshot is created in GitHub for the current status of the folder using **git commit** and **git push**
  - now we create the DVC pipeline (we can create both by terminal or manually as .yaml) for the first command in the pipeline its better to use terminal the command is **dvc run -n get_data -d get_data.py -o data_raw.csv --no-exec python get_data.py** here -n is the name of pipeline command -d for dependencies -o(-o is shorthand for --outs, you can use -O for --outs-no-cache it does not track the files in cache) for output file name --no-exec for not executing the command at this moment (dvc run runs the command by default as soon as it is created), this creates the dvc.yaml
  - for the rest pipeline commands we can add them manually to the dvc.yaml
  - next we can run the pipeline to see if it is working correctly with the command **dvc repro**
  - then we create the GitHub workflow file for the GitHub actions by creating a file in the .github/workflows with <any_name>.yaml
  - lastly we commit and push the current snapshot to GitHub.
