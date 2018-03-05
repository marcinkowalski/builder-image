# builder image - centos with java and maven

Build the builder image in the OpenShift namespace and store the image in the OpenShift Registry:

- oc login -u system:admin
- oc new-build https://github.com/marcinkowalski/builder-image.git  -n openshift --context-dir='image-sabre-assist' --name="image-sabre-assist"