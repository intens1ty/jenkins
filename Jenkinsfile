pipeline {
    agent any
    stages {
      stage ('Hello') {
        when {
            expression { $JOB_NAME == 'test1' }
        }
          steps {
          echo "test"
      }   
    }
  }
}
