# playbook-beatinstall

# Require the below script adding into Jenkins to remove old role and refresh with new role
echo "Refreshing ansible roles"
sudo ansible-galaxy remove role-beatinstall
sudo ansible-galaxy install -f -r roles/role-beatinstall.yml

Paramaters that are required to be fed in either in Jenkins or command line
-e "beats=metricbeat version=6.0.1 logstaship=test1 role=rabbitmq
beats: this is either metric/file etc
version: version you want to install
logstaship: name or ip of the logstash server
role: server role, e.g. RabbitMq, MongoDB. Reason is all have different agent YML files that are copied over form template directory.

GROUP_VARS/ALL
source variable is for the location of the rpm.
