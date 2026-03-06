pipeline{
  agent any
  stages{
    stage('Install Dependencies'){
      steps{
        git 'https://github.com/Kambhampati-Ranjith-kumar/Automated-CI-CD-Pipeline-for-Flask-Task-Manager-Application-using-Jenkins-and-AWS-EC2.git'}
    }
    stage('Run Tests'){
      steps{
        sh 'pytest'
      }
    }
    stage('Deploy Applications'){
      steps{
        sshagent(['AWS-login']){
          sh '''
          scp -r * ubuntu@34.234.65.137:/home/ubuntu/app/

          ssh ubuntu@34.234.65.137 "
          pkill -f app.py || true
          nohup python3 /home/ubuntu/app/app.py &
          "
          '''
        }
      }
    }
  }
}
