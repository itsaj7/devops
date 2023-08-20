pipeline{
  agent any

  tools {
    maven 'MyMaven'
  }

  stages {
    stage('Clonerepo') {
      steps {
        git 'https://github.com/itsaj7/devops.git'
      }
    }
    stage('Compile') {
      steps {
        sh 'mvn compile'
      }
    }
      stage(CodeReview) {
        steps {
          sh 'mvn pmd:pmd'
        }
      }
      stage(UnitTesting){
        steps {
          sh 'mvn test'
        }
      }
      stage('Codecoverage'){
        steps{
          sh 'mvn verify'
        }
      }
      stage('Package'){
        steps {
          sh 'mvn package'
        }
      }
    }
  }




          
