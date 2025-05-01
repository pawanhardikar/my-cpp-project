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
                    artifactPattern: 'build/Release/my_app.exe', //  artifactPattern
                    buildDir: 'build' //  buildDir parameter
                ) {
                    echo "Running post-build steps..."
                    createArtifact name: "my_executable", type: "exe"
                }
            }
        }
    }
}

