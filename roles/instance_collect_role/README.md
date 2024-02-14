Role Name
=========

Collect Kepler metrics from instance.

Role Variables
--------------

variable|description
---|---
kepler_model_server_image| Kepler Model Server image (default: quay.io/sustainable_computing_io/kepler_model_server:v0.7)
ami_id| AMI image ID used for building machine name
instance_type| Instance type used for building machine name
region| AWS region used for COS push
access_key| AWS access key used for COS push
secret_key| AWS access secret used for COS push

Dependencies
------------

amd_id and instance_type are needed to be set corresponding to result from create_instance role

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: ec2spot
      roles:
      - role: instance_collect_role
        vars:
          instance_type: i3.metal

License
-------

Apache License, Version 2.0
