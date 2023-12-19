import hudson.model.*
import io.jenkins.plugins.semver.SemanticVersion

@NonCPS
def loadClass(String className) {
    getClass().getClassLoader().loadClass(className)
}

node {

    stage('Versioning') {
        // Use Semantic Versioning plugin to determine the next version.
        def version = script {
            def semver = new loadClass('io.jenkins.plugins.semver.SemanticVersion').newInstance()
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
