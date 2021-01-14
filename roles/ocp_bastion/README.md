Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml):

    internet_connected: "no"

Whether or not the OCP installation will be internet-connected or not.  If it is internet-connected, the ansible role will pull the required images directly from quay.  Otherwise, if it will be a disconnected installation, it will pull images from a registry of your choosing.  See 'repo_url' variable below.

    removable_media_path: ""

Assuming the installation method will be disconnected, and that the images required will be manually copied from one system (used to download images) to another (used to perform the installation in the disconnected environment) using [removable media](https://docs.openshift.com/container-platform/4.6/installing/install_config/installing-restricted-networks-preparations.html#installation-mirror-repository_installing-restricted-networks-preparations), this is the full path where your removable media is mounted (e.g. /dev/sda1).

    architecture: x86_64

Note: this role has only been tested on x86_64 systems.

    cluster_name: ""

If your intended cluster and domain name is mycluster.bsaedomain.com, the cluster_name is *mycluster*.

    domain_name: ""

If your intended cluster and domain name is mycluster.bsaedomain.com, the domain name of your cluster is *basedomain.com*.

    install_name: ocp-install-dir

Intended name of the installation directory.

    install_dir: "/home/{{ ansible_env.USER }}/{{ install_name }}"

The full path of the intended installation directory.

    local_registry: ""

The registry domain name, and optionally the port, that your mirror registry uses to serve content (e.g. *myhostname:5000*)

    local_repository: ocp4/openshift4
    ocp_release: 4.6.6

Select OCP version in the form of 'X.Y.Z' (e.g. *4.6.6*).

    product_repo: openshift-release-dev
    pullsecret_email: ''

Specify the email address associated with your pull secret.

    release_name: ocp-release

    repo_url: "{{ ansible_default_ipv4.address }}"

Http server serving ignition configs

## Vcenter Information
    datacenter: dc01                 # vSphere datacenter where your cluster will live
    datastore: ds02                  # vSphere datastore for your cluster
    template_name: RHCOS_template    # the name of the RHCOS template in vSphere that will be used to create the cluster nodes
    vcenter_ip: 192.168.200.50       # wil more than likely be the ip address of your vcenter_server
    vcenter_server: myvcenter.com    # server name for vcenter
    vcenter_passwd: password         # password for your vcenter_user
    vcenter_user: humbe              # make sure to use an administrator user that can create resources
 

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
