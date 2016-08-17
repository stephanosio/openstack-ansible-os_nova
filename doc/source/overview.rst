CPU Platform Compatibility
~~~~~~~~~~~~~~~~~~~~~~~~~~

This role supports multiple CPU architecture types.  At least one repo_build
node must exist for each CPU type that is in use in the deployment.

Currently supported CPU architectures:
 - x86_64 / amd64
 - ppc64le


Compute Driver Compatibility
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This role supports multiple nova compute driver types.  The following
compute drivers are supported:
 - libvirt (default)
 - ironic
 - lxd (via nova-lxd)
 - powervm (via nova-powervm)

The driver type will automatically be detected by the OpenStack Ansible Nova
role for the following compute driver types:
 - libvirt
 - ironic
 - powervm

Any mix and match of compute node types can be used for those platforms.

If using the lxd driver, the compute type must be specified using the
``nova_virt_type`` variable in the ``/etc/openstack_deploy/user_variables.yml``
file.

.. code-block:: shell-session

   nova_virt_type: lxd

It should be noted that if the ``nova_virt_type`` variable is set, then all
nodes in the deployment will be set to that hypervisor type.  It is recommended
to allow the automatic hypervisor detection.
