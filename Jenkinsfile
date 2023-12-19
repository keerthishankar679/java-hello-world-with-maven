node {
    // Define the agent
    //stage('checkout') {
        // Checkout code from Git
        //checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/keerthishankar679/java-hello-world-with-maven.git']]])
    //}

    stage('build') {
        // Set up Maven and Java tools
        tool 'maven'
        tool 'java'

        // Build the project using Maven
        sh 'mvn clean install'
        archiveArtifacts artifacts: 'target/*.jar'
    }
}
