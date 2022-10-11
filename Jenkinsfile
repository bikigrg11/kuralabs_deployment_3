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
     post {
       // only triggered when blue or green sign
       success {
           slackSend(channel: 'alerts-testing', color: 'good', message: ":party_parrot: NOTIFICATION: BUILD SUCCESS  :party_parrot:")
       }
       // triggered when red sign
       failure {
           slackSend(channel: 'alerts-testing', color: 'RED', message: ":alarm_clock: NOTIFICATION: NEW RELEASE  WITH SOME FAILURE :alarm_clock:")
       }
      //  // trigger every-works
      //  always {
      //      slackSend ...
      //  }
    }
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
    stage ('Deploy'){
      agent{label 'awsDeploy'}
      steps {
        sh '''#!/bin/bash
        git clone https://github.com/kura-labs-org/kuralabs_deployment_2.git
        cd ./kuralabs_deployment_2
        python3 -m venv test3
        source test3/bin/activate
        pip install -r requirements.txt
        pip install gunicorn
        gunicorn --workers=4 application:app --bind=0.0.0.0 --daemon
        '''
      }
    }
  }
 }
