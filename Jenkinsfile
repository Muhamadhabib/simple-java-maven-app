node {  
    stage('Build') { 
      git url: 'https://github.com/cyrille-leclerc/multi-module-maven-project'
      withMaven(maven: 'mvn') {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') { 
      git url: 'https://github.com/cyrille-leclerc/multi-module-maven-project'
      withMaven(maven: 'mvn') {
        sh 'mvn test'
      }
    }
    // stage('Deploy') { 
    //     sh './jenkins/scripts/deliver.sh'
    // }
}