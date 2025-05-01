@Library('my-shared-library') _

pipeline {
    agent any
    stages {
        stage('Build C++ Project') {
            steps {
                cppBuild(
                    buildType: 'Release',
                    cmakeCommand: 'cmake -S. -Bbuild',
                    runTests: false
                ) {
                    stage('Post-Build') {
                        echo "Running post-build steps..."
                        createArtifact name: "my_executable", type: "exe"
                    }
                }
            }
        }
    }
}