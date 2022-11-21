node {  
    stage('Build') { 
      withMaven(maven: 'mvn') {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') { 
      withMaven(maven: 'mvn') {
        sh 'mvn test'
      }
    }
    // stage('Deploy') { 
    //     sh './jenkins/scripts/deliver.sh'
    // }
}