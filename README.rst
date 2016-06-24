OpenStack-Ansible Nova
######################

Ansible role that installs and configures OpenStack Nova and all of its
corresponding services.

Default Variables
=================

.. literalinclude:: ../../defaults/main.yml
   :language: yaml
   :start-after: under the License.


Required Variables
==================

.. code-block:: yaml
    # comma separated list of Glance internalUrls
    glance_api_servers: "http://glance_host:9292"


Example Playbook
================

.. code-block:: yaml
    - name: Playbook for deploying nova
      hosts: nova_all
      user: root
      roles:
        - { role: "os_nova" }
