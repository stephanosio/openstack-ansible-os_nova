===============================
Nova role for OpenStack-Ansible
===============================

.. toctree::
   :maxdepth: 2

   overview.rst
   app-powervm.rst

:tags: openstack, nova, cloud, ansible
:category: \*nix

This role will install the following Upstart services:
    * nova-server
    * nova-compute

Default Variables
^^^^^^^^^^^^^^^^^

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
