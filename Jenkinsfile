pipeline {
  agent none

  stages {
    stage("Build & Test") {
      matrix {
        agent {
          dockerfile {
            additionalBuildArgs """
              --build-arg NODE_VERSION=$NODE
            """.stripIndent().trim()
          }
        }
        axes {
          axis {
            name "NODE"
            values "10", "12", "14"
          }
        }
        stages {
          stage("Stage 1") {
            steps {
              sh "uname -a"
              sh "node -v"
            }
          }
          stage("Stage 2") {
            steps {
              sh "uname -a"
              sh "node -v"
            }
          }
        }
      }
    }
  }
}