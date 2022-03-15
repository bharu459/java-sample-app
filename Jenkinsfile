pipeline {
   agent any
        stages { 
            stage("Source Code checkout"){
               steps{
                   git branch: "newbranch", url: "https://github.com/bharu459/java-sample-app.git"
               }
           }    
        stage("BuildCode") {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Unit-Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Sonarqube Analysis') {
           steps {
                sh './bin/sonar-scanner'
           }
        }
        stage("Quality Gate") {
          steps {
             echo "wait for QG"
          }
        }
       stage ('Deploy To Prod') {
         steps {
             sh 'echo "Deploy into Prod"'
         }
       }
  } 
}
