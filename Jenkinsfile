node {

    stage('Versioning') {
        // Use Semantic Versioning plugin to determine the next version.
        def version = script {
            def semver = getClass().getClassLoader().loadClass('io.jenkins.plugins.semver.SemanticVersion').newInstance()
            semver.incSemVer()
        }
        echo "Next version: ${version}"
        // Optionally, you can store the version in an environment variable
        env.BUILD_VERSION = version
    }
    
    stage('build') {
        
        tool 'maven'
        tool 'java'
        
        sh 'mvn clean install -Drelease.version=${env.BUILD_VERSION}'
        archiveArtifacts artifacts: 'target/*.jar'
    }
}
