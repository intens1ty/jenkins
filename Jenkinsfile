pipeline {
    agent any
    environment {
        BUILD="$JOB_NAME"
    }
    stages {

      stage('Get code ansible') {
            steps {
              sh '''
              mkdir -p ansible
              '''
              dir('ansible') {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/intens1ty/jenkins.git']]])
              }
            }
        }

      stage ('Deploy') {
        when {
            expression { "$BUILD" == "Stage" }
        }
          steps {
          echo "test" 
          }
      }
         
      stage ('Rollback') {
        when {
            expression { "$BUILD" == "Stage" }
        }
          steps {
          echo "test"
          }
      }
    }
}
