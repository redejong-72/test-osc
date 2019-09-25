#!groovy
 
@Library('piper-lib-os') _
 
// The coordinates of the central pipeline script
def REPO
def BRANCH
def PATH
 
// In case access to the repository containing the central pipeline
// script is restricted the credentialsId of the credentials used for
// accessing the repository needs to be provided below. The corresponding
// credentials needs to be configured in Jenkins accordingly.
def CREDENTIALS_ID

REPO = 'https://github.com/alliander/SCP-pipelines.git'
BRANCH = 'WIP'
PATH = 'WIP/Jenkinsfile'
CREDENTIALS_ID = 'svc-jenkins-github'
 
node() {
 
    deleteDir()
 
    checkout scm
 
    setupCommonPipelineEnvironment(script: this)
 
    //pipelineExecute (script: this)
 
    // The coordinates of the central pipeline script
    //REPO = commonPipelineEnvironment.getConfigProperty('JENKINSFILE_GIT_URL')
    //BRANCH = commonPipelineEnvironment.getConfigProperty('JENKINSFILE_GIT_BRANCH')
    //PATH = commonPipelineEnvironment.getConfigProperty('JENKINSFILE_PATH')
 
    // In case access to the repository containing the central pipeline
    // script is restricted the credentialsId of the credentials used for
    // accessing the repository needs to be provided below. The corresponding
    // credentials needs to be configured in Jenkins accordingly.
    //CREDENTIALS_ID = commonPipelineEnvironment.getConfigProperty('JENKINSFILE_GIT_CREDENTIALS_ID')
}
 
echo "Launching pipeline '${PATH}' from '${BRANCH}@${REPO}' using credentialsId '${CREDENTIALS_ID}'."
 
pipelineExecute repoUrl: REPO, branch: BRANCH, path: PATH, credentialsId: CREDENTIALS_ID

//pipelineExecute (script: this)
