node {

    stage('build') {
        
        tool 'maven'
        tool 'java'

        sh 'mvn build-helper:parse-version versions:set@major'
        sh 'mvn build-helper:parse-version versions:set@minor'
        sh 'mvn build-helper:parse-version versions:set@patch'
        sh 'mvn clean install'
        archiveArtifacts artifacts: 'target/*.jar'
    }
}
