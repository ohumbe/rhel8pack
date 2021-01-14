## Ansible Role: OCP4 UPI

Ansible Role for UPI installation of Openshift in internet-connected and internet-disconnected (i.e. 'air-gapped') environments.

### Requirements

### Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml):

### Instructions

- Before running the ansible playbook, make sure to edit the variables in the vars/main.yml file.  The values entered there only serve as examples.  Replace those values with the correct or intended values - otherwise the playbook WILL FAIL.  All of these variables are either chosen by you, for example in the case of the name for your cluster directory, or are related to vSphere.

- To run the ansible playbook, issue this command from the automation directory containing the `deploy_ocp.yaml` file: ansible-playbook deploy_ocp.yaml
