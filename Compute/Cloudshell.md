Cloud shell provides the following:

Temporary Compute Engine VM
Command-line access to the instance via a browser
5 GB of persistent disk storage ($HOME dir)
Pre-installed Cloud SDK and other tools
gcloud: for working with Compute Engine and many Google Cloud services
gcloud storage: for working with Cloud Storage
kubectl: for working with Google Kubernetes Engine and Kubernetes
bq: for working with BigQuery
Language support for Java, Go, Python, Node.js, PHP, and Ruby
Web preview functionality
Built-in authorization for access to resources and instances


Create a bucket via Gcloud
gcloud storage buckets create gs://singarajtestnew
Copy:-
gcloud storage cp test.txt gs://singarajtestnew

Create a persistent state in Cloud Shell

INFRACLASS_REGION=us-east1
echo $INFRACLASS_REGION
mkdir infraclass
touch infraclass/config
echo INFRACLASS_REGION=$INFRACLASS_REGION >> ~/infraclass/config
INFRACLASS_PROJECT_ID=qwiklabs-gcp-01-084d27d2494b
echo INFRACLASS_PROJECT_ID=$INFRACLASS_PROJECT_ID >> ~/infraclass/config
source infraclass/config
echo $INFRACLASS_PROJECT_ID


vi .profile

add the below line
source infraclass/config
:!wq

echo $INFRACLASS_PROJECT_ID
