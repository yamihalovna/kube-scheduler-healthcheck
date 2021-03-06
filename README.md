# kube-scheduler-healthcheck
A docker container intended to be a healthcheck for the kubernetes scheduler. All the container will do is create a pod, wait for it to be scheduled (i.e leave `Pending` state), then delete the pod.

# Config
The following environment variables can be set:

| Name                        | description                                                                                         | default       | example                         |
|-----------------------------|-----------------------------------------------------------------------------------------------------|---------------|---------------------------------|
| `TEST_POD_NAMESPACE` |  The namespace in which to create the pod  | kube-system | kube-system |
| `TEST_POD_IMAGE`        | The image to use when creating the test pod | gcr.io/google_containers/pause:3.0 | gcr.io/google_containers/pause:3.0   
| `TEST_POD_NAME_POSTFIX`        | Optional postfix to add to the name of the test pod. Pod name will be `scheduler-healthcheck-<postfix>`  | pod | mysuperpostfix  
