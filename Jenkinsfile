pipeline{
  agent any
  stages{   
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
