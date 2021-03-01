
Configuration
=============

Server parameters
-----------------

The "server" lives on the callee side.

Required:
 - `port` (int): Port to bind to

Client parameters
-----------------

The "client" lives on the caller side.

Required:
 - `server` (string): Hostname or IP address of the server machine
 - `port` (int): Port to connect to
 - `services` (list): List of services to advertise & transmit (see below)

Optional:
  - `timeout` (float): Timeout after which a service call is considered as failed	 - `timeout` (int): Timeout after which a service call is considered as failed
    (UDP only, default: 10.0)	   (UDP only, default: 5)
  - `service_prefix` (string): prepend service_prefix before advertised service names (TCP only, default is empty string). This is a feature to allow to prefix service names with a string without changing the service name on the server side. Therefore the `services` parameter `name` must match the name advertised on the server side.

Service configuration
---------------------

The `services` parameter contains a list of services to be transmitted.
Available parameters per service:

Required:
 - `name` (string): Service name (e.g. `"/my_service"`)
 - `type` (string): Service type (e.g. `"std_srvs/Empty"`)
