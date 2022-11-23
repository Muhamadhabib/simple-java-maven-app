node {  
  withDockerContainer(args: '-v /root/.m2:/root/.m2', image: 'maven:3-alpine') {
    stage('Build') { 
      // withMaven {
        sh 'mvn -B -DskipTests clean package'
      // }
    }
    stage('Test') { 
      // withMaven {
        sh 'mvn test'
      // }
    }
  }
}