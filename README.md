crc
...................................................

crc console --credentials

crc oc-env







oc
..............................................................



oc get nodes

oc api-version

oc cluster-info

oc whoami show-console

oc describe pod test-pod

oc run test --image nginx

oc get pods -o wide

oc status

oc get routes -n openshift

oc get pods -o wide

oc get pods -A

oc get pods --all-namespaces

oc label pod demopod dev=test

oc get pods --selector dev=test

oc api-resources

oc api-resources --namespaced==true --api-group ""

oc get projects 

oc adm top

oc adm top pod -A

oc adm top pod -A --sum --sort-by cpu

oc adm top pod -A --containers

oc logs pod/alertmanager-main-0 -n openshift-monitoring 

oc debug node/crc

oc image info \
registry.lab.example.com:8443/redhattraining/docker-nginx:1.23

oc delete pod docker-nginx

oc get events

oc get templates -n openshift

oc process -f mysql-template.yaml -o yaml

oc process -f mysql-template.yaml --parameters

oc set env deployment/my-app TEAM=red

watch oc get pods

oc set env deployment/my-db \
MYSQL_USER=developer \
MYSQL_PASSWORD=developer \
MYSQL_DATABASE=sampledb









troubleshooting 
..........................................................................


Use these tools to validate the functions and environment for a running container:

oc describe: Display the details of a resource.

oc edit: Edit a resource configuration by using the system editor.

oc patch: Update a specific attribute or field for a resource.

oc cp: Copy files and directories to and from containers.

oc exec: Execute a command within a specified container.

oc port-forward: Configure a port forwarder for a specified container.

oc logs: Retrieve the logs for a specified container.

oc rsync: Synchronize files and directories to and from containers.

oc rsh: Start a remote shell within a specified container.

oc get endpointslices

oc extract secret/demo-secret -n demo \
--to /tmp/demo --confirm





random
....................................................................




systemctl status kubelet


chroot /host


crictl ps --name postgresql


crictl inspect --output go-template \
--template '{{.info.pid}}' 27943ae4f3024



.............................................................................................

Store the IP address of the MariaDB pod as a variable for use in the next substep, and print the DB_IP variable value.

[student@workstation ~]$ DB_IP=$(oc get pods my-db-688764b8c7-9k92j \
-o=jsonpath='{.status.podIP}') && echo $DB_IP
10.8.0.89









