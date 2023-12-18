node {
    // Define the agent
    stage('Checkout') {
        // Checkout code from GitHub
        git url: 'https://github.com/keerthishankar679/java-hello-world-with-maven.git', credentialsId: 'github access'
    }

    stage('Build') {
        // Set up Maven tool
        tool 'maven'
        tool 'java'
        
        // Build the project using Maven
        sh 'mvn clean package'
    }
}

