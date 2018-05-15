node {
  checkout scm
  env.PATH = "${tool 'Maven3'}/bin:${env.PATH}"
  stage('Package') {
    dir('webapp') {
      sh 'mvn clean package -DskipTests'
    }
  }

  stage('Create Docker Image') {
    dir('webapp') {
      sh "sudo docker build -t arungupta/docker-jenkins-pipeline:2 ."
    }
  }
}
