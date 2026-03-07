pipeline{
  agent any
  stages{
    stage('Install Dependencies') {
      steps{
        sh 'pip3 install --break-system-packages -r requirements.txt'
      }
    }
    stage('Run Tests'){
      steps{
        sh 'python3 -m pytest'
      }
    }
    stage('Deploy Applications'){
      steps{
        sshagent(['AWS-login']){
          sh '''
          scp -o StrictHostKeyChecking=no ubuntu@54.85.107.229:/home/ubuntu/app/

          ssh -o StrictHostKeyChecking=no ubuntu@54.85.107.229 "
          pkill -f app.py 2>/dev/null || true 
          nohup python3 /home/ubuntu/app/app.py > /dev/null 2>&1 &
          "
          '''
        }
      }
    }
  }
}
