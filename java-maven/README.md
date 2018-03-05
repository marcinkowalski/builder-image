# builder image - centos with java and maven

Build the builder image in the OpenShift namespace and store the image in the OpenShift Registry:

- oc login -u system:admin
- oc new-build https://sg0922019:trinity1@git.sabre.com/scm/lp/builder-image.git -n openshift --context-dir='java-maven' --name="java-maven"