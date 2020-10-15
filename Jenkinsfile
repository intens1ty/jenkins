pipeline {
    agent any
    environment {
        BUILD="$JOB_NAME"
    }
    stages {

      stage('Get code ansible') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/intens1ty/jenkins.git']]])
            }
        }

      stage ('Deploy') {
        when {
            expression { "$BUILD" == "Stage" }
        }
          steps {
          sh """
            cd ansible
            ansible-galaxy install -p roles ansistrano.deploy ansistrano.rollback
            ansible-playbook -i inventory/hosts.ini \
                        -e "ansistrano_deploy_via=git" \
                        -e "ansistrano_git_repo=https://github.com/intens1ty/3proxy.sh" \
                        deploy.yml
          """
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
