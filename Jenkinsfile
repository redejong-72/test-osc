@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('static checks') {
        artifactSetVersion script: this, buildTool: 'mta'
        npmExecute script: this, dockerImage: 'node:8-stretch', npmCommand: 'run test --if-present'
   }
    stage('build') {
        mtaBuild script: this
   }
    stage('write stats') {
        influxWriteData script: this
   }
}
