===============================
Nova role for OpenStack-Ansible
===============================

.. toctree::
   :maxdepth: 2

   configure-nova.rst
   app-powervm.rst

:tags: openstack, nova, cloud, ansible
:category: \*nix

This role will install the following Upstart services:
    * nova-server
    * nova-compute

Default variables
~~~~~~~~~~~~~~~~~

.. literalinclude:: ../../defaults/main.yml
   :language: yaml
   :start-after: under the License.

Example playbook
~~~~~~~~~~~~~~~~

.. literalinclude:: ../../examples/playbook.yml
   :language: yaml

Tags
~~~~

This role supports two tags: ``nova-install`` and ``nova-config``

The ``nova-install`` tag can be used to install and upgrade.

The ``nova-config`` tag can be used to manage configuration.

CPU platform compatibility
~~~~~~~~~~~~~~~~~~~~~~~~~~

This role supports multiple CPU architecture types.  At least one repo_build
node must exist for each CPU type that is in use in the deployment.

Currently supported CPU architectures:
 - x86_64 / amd64
 - ppc64le

At this time, ppc64le is only supported for the Compute node type. It can not
be used to manage the OpenStack-Ansible management nodes.


Compute driver compatibility
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This role supports multiple nova compute driver types.  The following
compute drivers are supported:
 - libvirt (default)
 - ironic
 - lxd (via nova-lxd)
 - powervm (via nova-powervm)

The driver type is automatically detected by the OpenStack Ansible Nova role
for the following compute driver types:
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
