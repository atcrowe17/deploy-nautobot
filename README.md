# nautobot builder  
Use to build a production Nautobot server with Ansible.  

## prerequisites

1. Deploy a fresh Ubuntu 22.04.1 LTS server. This will be the Nautobot server.
2. Ensure the server has internet access and is reachable from the Ansible server.

## deployment 
1. Builds a standalone Nautobot server. 
2. Installs local Postgres database, Nginx web server, and Redis cache.
3. Generates and installs self-signed SSL certificate.
4. Creates a local user account on the Naubot server for system management.
5. Creates one superuser account for Nautobot app.
6. Creates a single Postgres database and user.

## tested environment  

Ansible Server  
1. Ansible Version = 2.13.13  
2. Operating System = Ubuntu 20.04.5 LTS  

Nautobot Server  
1. Operating System = Ubuntu 22.04.1 LTS

## default settings
Nautobot Version = 2.1.2  
Nautobot Home Directory = ```/opt/nautobot```  
NodeJS Version = 18  
Database = Postgres  
Nautobot Plugins = nautobot_bgp_models, napalm  
Ansible Vars = ```example_host.yml``` 

## setup
1. Clone the repository to your Ansible server.
2. Create copy of ```/host_vars/example_host.yml``` and update with deployment specific settings.
3. Update the ```inventory.ini``` file with the Nautobot server IP address and root username/password.
4. Run the playbook. ```ansible-playbook -i inventory.ini build-nautobot-server.yml```

## non-default deployments
If deploying a non-default version of Nautobot, check the installation guide for that version and update the Ansible playbook accordingly. Too many unknowns to cover every case. As a general rule, compare install guide requirements with all files in the ```/files``` directory, dependencies installed within the playbook, and defaults in ```/host_vars/example_host.yml```.

## references

Nautobot Installation Guide - https://docs.nautobot.com/projects/core/en/latest/user-guide/administration/installation/

# Support Contacts

Ty Crowe  
email: ty@aopinc.com  
slack: tyc17afguy@gmail.com  
