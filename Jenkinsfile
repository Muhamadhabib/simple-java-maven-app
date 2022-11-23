node {  
  withDockerContainer(args: '-v /root/.m2:/root/.m2', image: 'maven:3-alpine') {
    stage('Build') { 
      sh 'mvn -B -DskipTests clean package'
    }
    stage('Test') {
      sh 'mvn test'
    }
  }
  withDockerContainer(args: '-p 3000:3000') {
    stage('Deliver') {
      sh './jenkins/scripts/deliver.sh'
    }
  }
}