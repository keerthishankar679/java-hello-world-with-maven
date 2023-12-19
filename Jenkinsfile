node {

    stage('build') {
        
        tool 'maven'
        tool 'java'
        
        sh 'mvn clean install'
        archiveArtifacts artifacts: 'target/*.jar'
    }
}
