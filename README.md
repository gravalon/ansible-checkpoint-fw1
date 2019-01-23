# ansible-checkpoint-fw1
Ansible playbooks/roles/tasks and what have you to build and configure Checkpoint Gateways &amp; Managers 

This is a work in progress, so use it at your own risk
spelling is always optional

Easier said than done, as Checkpoint really don't make life easy for you.

Whilst there is a limited python interpreter installed as part of the install, it has limited libraries included and the script name needs to be included in a whitelist file....wild cards do NOT work!
So all commads to be run on the remote host need to be executed as raw, making verification and error handling problematic.

THe CP command to apply the initial system configuration "config_system" kills the SSH connection on completion, which ansible treats as host unreachable and errors out the playbook
Sigh

What we have so far

Generate config templates and apply then for:
 - Standalone Gateway
 - Cluster Gateway
 - Primary Manager
 - Secondary Manager
 - Primary Domain Manager
 - Secondary Domain Manager
 - Domin Logger

Apply HFA (Updating Deployment Agent if necessary)

Apply Interface/Static Routing configuration based on YAML config file

Gateway Config:
 - Enable CP SNMP daemon

Manager Config:
 - (Nothing at this time)
 
General Config applied to all devices:
 - SNMP Configuration
 - (Whatever else might be useful, like authentication/users etc)

