@Library('my-shared-library') _

pipeline {
    agent any
    stages {
        stage('Build C++ Project') {
            steps {
                cppBuild(
                    buildType: 'Release',
                    cmakeCommand: 'cmake -S. -Bbuild -DCMAKE_BUILD_TYPE=Release',
                    runTests: false,
                    artifactPattern: 'build/bin/my_app' //Add artifactPattern here
                ) {
                    echo "Running post-build steps..."
                    createArtifact name: "my_executable", type: "exe"
                }
            }
        }
    }
}
