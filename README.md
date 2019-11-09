# python-docker-app
python-docker-app

How to run a docker container with Newrelic key and enable monitoring

docker run -p 5000:5000 -e NEW_RELIC_LICENSE_KEY=xxxxx -e NEW_RELIC_APP_NAME=python-app manee2k6/py-newrelic

# To run in kubernetes cloud:

  Use the deployment yaml latest created above:
  
  Follow this steps:
  
  1. clone python app repo on local
2. build the docker image
3. tag image(account/repository and push to docker hub)
4.Push the image to hub
5. Create k8s deployment resource yaml.
6. get the raw url and fire kubectl commands.
   kubectl create -f RAW_URL




