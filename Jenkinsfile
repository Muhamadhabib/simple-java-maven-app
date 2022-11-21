node {  
    stage('Build') { 
        sh 'mvn -B -DskipTests clean package'
    }
    stage('Test') { 
        sh 'mvn test'
    }
    // stage('Deploy') { 
    //     sh './jenkins/scripts/deliver.sh'
    // }
}