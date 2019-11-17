node{
   
   stage(" Code Checkout"){
      echo 'App build started..'
      git credentialsId: 'githubID', url: 'https://github.com/Project-purpose/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker build -t yesh .
     sh 'docker tag yesh ashhh24/python-newrelic'
     sh 'docker push ashhh24/python-newrelic'
     sh 'docker run -p 5000:5000 -e NEW_RELIC_LICENSE_KEY=8eace5d26308bc09425b65917608d733174f4c33 -e NEW_RELIC_APP_NAME=python-app ashhh24/python-newrelic'
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag ashhh24/python-newrelic ashhh24/python-newrelic:dev'
          sh 'docker push ashhh24/python-newrelic:dev'
          sh 'docker push ashhh24/python-newrelic:latest'
      }
    }
    stage("App deployment started"){
     //sh 'oc login --token=t01XSPheqChA1n1QxmPCSJAwm5rFNYzb7FvRP9mmg6A --server=https://api.us-east-1.online-starter.openshift.com:6443'
          // sh 'oc new-project creativetech'
      
    // sh 'oc new-app shiddu/pythonimage:dev --name python --env NEWRELIC_LICENSE=xxxxxx NEWRELIC_APPNAME=pyapp'
    // sh 'oc expose svc python --name=python'
    // sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   


   
























}
