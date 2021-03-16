
## Run with created Folder by JCasC
docker run --rm \
	-v $(pwd)/demo/job-folders/JenkinsfileWithLibraryCall:/workspace/Jenkinsfile:z \
	-v $(pwd)/demo/job-folders/folderTemplate.yaml:/usr/share/jenkins/ref/casc/folderTemplate.yaml:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name myFolder/myJob
	
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	-v $(pwd)/demo/job-folders/folderTemplate.yaml:/usr/share/jenkins/ref/casc/folderTemplate.yaml:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name folderWithoutLib/exampleJob
	
	
## Create folder without jobDSL
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name folder1/folder2/myJob
	
## Run without folders
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev \
	--job-name myJob
	
## Run without name
docker run --rm \
	-v $(pwd)/demo/job-folders/Jenkinsfile:/workspace/Jenkinsfile:z \
	localhost/jenkins4eval/jenkinsfile-runner:dev
	


