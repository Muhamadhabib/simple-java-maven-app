node {  
    stage('Build') { 
      withMaven {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') { 
      withMaven {
        sh 'mvn test'
      }
    }
    // stage('Deploy') { 
    //     sh './jenkins/scripts/deliver.sh'
    // }
}