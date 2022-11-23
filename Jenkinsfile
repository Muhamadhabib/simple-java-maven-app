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
  }
  withDockerContainer(args: '-p 3000:3000') {
    stage('Deliver') {
      checkout scm
      sh 'docker run --rm -v /var/jenkins_home/workspace/java-app/jenkins/scripts/deliver.sh'
    }
  }
}