node {
    // Define the agent
    stage('Checkout') {
        // Checkout code from GitHub
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/keerthishankar679/java-hello-world-with-maven.git']]])
    }

    stage('Build') {
        // Set up Maven tool
        tool 'maven'

        // Build the project using Maven
        sh 'mvn clean install'
    }
}
