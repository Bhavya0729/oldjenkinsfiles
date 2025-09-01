pipeline {
    agent any

    stages {
        stage('continous download') {
            steps {
                git branch: 'main', url: 'https://github.com/Bhavya0729/Maven.git'
            }
        }

        stage('continous build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('continous deployment') {
        steps{
     sh '''
            scp /var/lib/jenkins/workspace/declarativepipeline-java/Helloworld.java \
            ubuntu@172.31.44.38:/home/ubuntu/pen/Helloworld.java
        '''
}
    }
stage ('continous testing')
        {
            steps
            {
               sh """
  javac /var/lib/jenkins/workspace/declarativepipeline-java/Helloworld.java
  java -cp /var/lib/jenkins/workspace/declarativepipeline-java Helloworld
"""
}
}
stage('continous release') {
        steps{
     sh '''
            scp /var/lib/jenkins/workspace/declarativepipeline-java/Helloworld.java \
            ubuntu@172.31.42.163:/home/ubuntu/pen/Helloworld.java
        '''
}
    }
    }
    }
