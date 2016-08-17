`Home <index.html>`_ OpenStack-Ansible Neutron

=====================================
Scenario - Using PowerVM Nova plugin
=====================================

Prerequisites
~~~~~~~~~~~~~

In order to use the PowerVM OpenStack drivers with OpenStack-Ansible (OSA), the
following pre-requisites must be fulfilled:

 - At least one of the repo-build servers must be ppc64le. Can mix and match
   repo-build servers between x86 and ppc64le.

 - The compute nodes should be pre-configured for PowerVM with the NovaLink_
   feature.

 - The NovaLink Management VM needs at least one direct attach I/O card.
   OpenStack Ansible is currently able to deploy the PowerVM drivers when
   paired with the Linux Bridge or Open vSwitch agent. The traditional PowerVM
   Shared Ethernet Adapter networking agent is not yet supported.

 - The network topology on the NovaLink must match a supported OpenStack
   Ansible network configuration.

.. _NovaLink: http://www.ibm.com/support/knowledgecenter/POWER8/p8eig/p8eig_kickoff.htm?cp=POWER8


PowerVM configuration
~~~~~~~~~~~~~~~~~~~~~

The Compute driver for OpenStack-Ansible should automatically detect that it
is of type PowerVM. If the user has specified a specific compute type, that
is applicable to the whole cloud. It is advised that the deployer allows
OSA to detect the appropriate compute node type.
