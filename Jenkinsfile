node {  
    stage('Build') { 
      withMaven(maven: 'maven-3', mavenLocalRepo: '.repository', mavenSettingsConfig: 'my-maven-settings') {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') { 
      withMaven(maven: 'maven-3', mavenLocalRepo: '.repository', mavenSettingsConfig: 'my-maven-settings') {
        sh 'mvn test'
      }
    }
    // stage('Deploy') { 
    //     sh './jenkins/scripts/deliver.sh'
    // }
}