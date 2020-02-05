# openshiftv4.2-workshop

# Test local

cd /Users/sbriand/Documents/Team/Sales/Countryman/Accounts/Sysco/Supplies/Workshops/Developer/4.2-Workshop/openshiftv4-workshop

docker run -it --rm -p 8080:8080 -v $(pwd):/openshiftv4-workshop -e CONTENT_URL_PREFIX="file:///openshiftv4-workshop" -e WORKSHOPS_URLS="file:///openshiftv4-workshop/_ocp_intro_workshop.yml" -e LOG_TO_STDOUT=true quay.io/osevg/workshopper              

# OCP Deployment
oc login <API URL>

oc new-app quay.io/osevg/workshopper --name=intro4workshop -e WORKSHOPS_URLS="https://raw.githubusercontent.com/esbriand/openshiftv4-workshop/ocp4.2/_ocp_intro_workshop.yml" -e LOG_TO_STDOUT=true 

oc expose svc/intro4workshop