pipeline{
agent any
  stage ('Codecompiling'){
  steps{ 
    withmaven(maven: 'maven'){
    sh 'mvn clean compile'
            }
  }
  }
stage ('Testing '){
  steps{ 
    withmaven(maven: 'maven'){
    sh 'mvn test'
            }
  }
  }
  stage ('Deploy'){
  steps{ 
    withmaven(maven: 'maven'){
    sh 'mvn deploy'
            }
  }
  }
}
