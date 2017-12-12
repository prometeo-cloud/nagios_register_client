# nagios_register_client

## Description:

This role Register and Unregister a Nagios client from the Nagios Server.

## Behaviour:

Registering the Nagios client with Nagios Server.

**Feature:** Register a Nagios Client with Nagios Server  
- **Given** a Nagios Server Hostname to a new nagios client
- **Given** a flag name task_type "Register"
- **When** deployment is executed
- **Then** Nagios client is register with Nagios Server  

Unregistering the Nagios client from Nagios Server.

**Feature:** Unregister a Nagios Client from Nagios Server  
- **Given** a Nagios Server Hostname to a new nagios client
- **Given** a flag name task_type "Unregister"
- **When** deployment is executed
- **Then** Nagios client is unregister with Nagios Server 

## Configuration:

Variable required upon execution of the role (not in the vars or defauls folders).
Needs to be provided to the role before execution.

| Variable  | Description  | Example  | 
|---|---|---|
| **nagios_server_hostname** | The Nagios Server Hostname |  |
| **nagios_client_hostname** | The Nagios Client Hostname |  |
| **nagios_clientip_address** | The Nagios Client IP address | |
| **task_type** | Register/Unregister Nagios client | Depend on the task type we can select type.

## Usage:

How to invoke the role from a playbook:

```yaml
- name: Registering/Unregister the Nagios Client              
  include_role:
    name: nagios_register_client
  vars:
    nagios_server_hostname: '?'
    nagios_client_hostname: '?'
    nagios
    task_type: '?'
   
```