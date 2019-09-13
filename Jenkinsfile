@Library('piper-lib-os') _
node() {
    durationMeasure (script: this, measurementName: 'build_duration') {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('static checks') {
        artifactSetVersion script: this, buildTool: 'mta'
        npmExecute script: this, dockerImage: 'node:8-stretch', npmCommand: 'audit fix'
        //sonarExecuteScan script: this
   }
    stage('build') {
        mtaBuild script: this
   }
    stage('write stats') {
        influxWriteData script: this 
  }
}
}
