pipeline {
  agent any
   stages {
    stage ('Build') {
      steps {
        sh '''#!/bin/bash
        python3 -m venv test3
        source test3/bin/activate
        pip install pip --upgrade
        pip install -r requirements.txt
        export FLASK_APP=application
        flask run &
        '''
     }
    //  post {
    //    // only triggered when blue or green sign
    //    success {
    //        slackSend(channel: 'alerts-testing', color: 'good', message: ":party_parrot: NOTIFICATION: BUILD SUCCESS  :party_parrot:")
    //    }
    //    // triggered when red sign
    //    failure {
    //        slackSend(channel: 'alerts-testing', color: 'RED', message: ":alarm_clock: NOTIFICATION: NEW RELEASE  WITH SOME FAILURE :alarm_clock:")
    //    }
    //}
   }
    stage ('test') {
      steps {
        sh '''#!/bin/bash
        source test3/bin/activate
        py.test --verbose --junit-xml test-reports/results.xml
        ''' 
      }
    
      post{
        always {
          junit 'test-reports/results.xml'
        }
       
      }
    }
    stage ('Clean'){
      agent{label 'awsDeploy'}
      steps{
        sh '''#!/bin/bash
        if [[ $(ps aux | grep -i "gunicorn" | tr -s " "| head -n 1 | cut -d " " -f 2) != 0 ]]
        then
          ps aux | grep -i "gunicorn" | tr -s " " | head -n 1 | cut -d " " -f 2 > pid.txt
          kill $(cat pid.txt)
          exit 0
        fi
        '''
      }
    }
    stage ('Deploy'){
      agent{label 'awsDeploy'}
      steps {
        keepRunning{
          sh '''#!/bin/bash
          pip install -r requirements.txt
          pip install gunicorn
          gunicorn --workers=4 application:app --bind=0.0.0.0 --daemon
          '''
        }
      }
    }
  }
 }
