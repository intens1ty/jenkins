pipeline {
    agent any
    environment {
        BUILD="$JOB_NAME"
    }
    stages {

        stage('Get code ansible') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: 'master']],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'ansible']],
                    submoduleCfg: [],
                    userRemoteConfigs: [[url: 'https://github.com/intens1ty/jenkins.git']]
                ])
            }
        }

      stage ('Deploy') {
        when {
            expression { "$BUILD" == "Stage" }
        }
          steps {
          echo "test" 
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
