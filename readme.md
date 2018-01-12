# nagios_register_client

## Description:

This role registers or unregisters a Nagios client with the Nagios Server.  It is run on the Nagios Server.

## Behaviour:

Registering the Nagios client with Nagios Server.

**Feature:** Register a Nagios Client with Nagios Server  
- **Given** a Nagios Server
- **Given** a new client to be registered
- **Given** a flag name task_type "Register"
- **When** role is executed on the Nagios server
- **Then** Nagios client is register with Nagios Server  

Unregistering the Nagios client from Nagios Server.

**Feature:** Unregister a Nagios Client from Nagios Server  
- **Given** a Nagios Server
- **Given** an existing client to be unregistered
- **Given** a flag name task_type "Unregister"
- **When** role is executed on the Nagios Server
- **Then** Nagios client is unregistered from Nagios Server 

## Configuration:

Variable required upon execution of the role (not in the vars or defauls folders).
Needs to be provided to the role before execution.

| Variable  | Description  | Example  | 
|---|---|---|
| **nagios_server_hostname** | The Nagios Server Hostname |  |
| **nagios_client_hostname** | The Nagios Client Hostname |  |
| **nagios_clientip_address** | The Nagios Client IP address | |
| **task_type** | Selects whether to register or unregister a client. | `register` or `unregister` |

## Usage:

How to invoke the role from a playbook:

```yaml
- name: Register/Unregister a client on Nagios server
  hosts: nagios-server
  become: yes
  tasks:
    - name: Register/Unregister a Nagios Client              
      include_role:
        name: nagios_register_client
      vars:
        nagios_server_hostname: '?'
        nagios_client_hostname: '?'
        nagios_clientip_address: '?'
        task_type: '?'
```
