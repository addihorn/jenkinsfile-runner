Job Folders demo
=================

This demo shows, how to define the Job inside of a folder-structure, defined by parameter ```--job-name```
To create folders, that load libraries JCasC can be used.


## Run with created Folder by JCasC (with Docker)  

To run in folders without assigned shared libraries  

```bash
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	-v $(pwd)/demo/job-folders/folderTemplate.yaml:/usr/share/jenkins/ref/casc/folderTemplate.yaml:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name folderWithoutLib/exampleJob
```	

To run in folders with assigned shared libraries  

```bash
docker run --rm \
	-v $(pwd)/demo/job-folders/JenkinsfileWithLibraryCall:/workspace/Jenkinsfile \
	-v $(pwd)/demo/job-folders/folderTemplate.yaml:/usr/share/jenkins/ref/casc/folderTemplate.yaml \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name myFolder/myJob
```
	
## Create folder without JCasC

```bash
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name folder1/folder2/myJob
```	

## Run names job without folders

```
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name myJob
```

## Run without name
```
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev
```