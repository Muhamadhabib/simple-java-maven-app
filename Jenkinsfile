node {  
  withDockerContainer(args: '-v /root/.m2:/root/.m2', image: 'maven:3-alpine') {
    stage('Build') { 
      checkout scm
      sh 'mvn -B -DskipTests clean package'
    }
    stage('Test') {
      checkout scm
      sh 'mvn test'
      junit 'target/surefire-reports/*.xml'
    }
    stage('Manual Approval') {
      input message: 'Lanjutkan ke tahap Deploy?'
      checkout scm
      sh './jenkins/scripts/deliver.sh'
    }
    stage('Deliver') {
      checkout scm
      sh './jenkins/scripts/deliver.sh'
      sleep time: 1, unit: 'MINUTES'
    }
  }
}