node {

    stage('build') {
        
        tool 'maven'
        tool 'java'

        //sh 'mvn build-helper:parse-version versions:set -DnewVersion=\${parsedVersion.majorVersion}.\${parsedVersion.minorVersion}.\${parsedVersion.nextIncrementalVersion} versions:commit'
        sh 'mvn clean install'
        archiveArtifacts artifacts: 'target/*.jar'
    }
}
