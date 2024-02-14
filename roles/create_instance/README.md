Role Name
=========

Collect Kepler metrics from spot instance.

Requirements
------------

- [AWS Command Line Interface](https://aws.amazon.com/cli/) installation
- boto modules: `pip install botocore boto3`
- Private key file for accessing instance: `kepler-ci-key.pem`

Role Variables
--------------

variable|description
---|---
region| AWS region used 
access_key| AWS access key 
secret_key| AWS access secret 
secuirty_group| security group of spot instance
volume_size| root volume size of instance (default: 120)
ami_id| AMI image ID
instance_type| Instance type

Example Playbook
----------------

Create a new spot instance:

    - hosts: localhost
      roles:
      - role: create_instance
        vars:
          instance_type: i3.metal


Add host from an existing list of spot instance requests:

    hosts: local
    tasks:
    - include_role:
        name: create_instance
      loop:
      - { instance_type: i3en.metal, request_id: sir-xxx }
      - { instance_type: i3.metal, request_id: sir-yyy }
      vars:
        instance_type: "{{ item.instance_type }}"
        set_request_id: "{{ item.request_id }}"

License
-------

Apache License, Version 2.0
