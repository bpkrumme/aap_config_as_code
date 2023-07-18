# aap_config_as_code

Configuration as code demo repository - currently a work in progress

##  Demo Environment

This repo includes environments for two separate AAP installations in disparate networks and as such uses `extra_vars` passed on the CLI depending on which network we are operating in.  There are several requirements necessary to use the examples here.

### Inventory

You will need to update the yaml-based Ansible Inventory file(s) `hosts.yml` and/or `hosts_mobile.yml` in order to run the automations.  Feel free to use the inventory files included as examples.  I find it easiest to have a utility server which performs the installation and configuration operations.  The architecture of your AAP environment is up to you and the variables in `install_vars` will need to be updated to reflect your desired inventory for the AAP installer.  You can find more information on how to configure these variables in the Red Hat Community of Practice validated collections:

|                                      Collection Name                                       |                 Purpose                  |
|:------------------------------------------------------------------------------------------:|:----------------------------------------:|
| [Controller Configuration](https://github.com/redhat-cop/controller_configuration) |   Automation controller configuration    |
|             [EE Utilities](https://github.com/redhat-cop/ee_utilities)             | Execution Environment creation utilities |
|     [AAP installation Utilities](https://github.com/redhat-cop/aap_utilities)      |  Ansible Automation Platform Utilities   |
|   [AAP Configuration Template](https://github.com/redhat-cop/aap_configuration_template)   |  Configuration Template for this suite   |

### install_vars/*/vault.yml

The `vault.yml` files include encrypted credentials and should be replaced using the data from your environment and subsequently encrypted using `ansible-vault`
A sample `vault.yml.example` file is included in the root of the repository for convenience.

## Running the installer playbook

Once you've updated all of the inventory, variables, and vaulted credentials