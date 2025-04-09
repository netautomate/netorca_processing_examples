# WideIP Service

This will create a WideIP (GTM) service for cross DC load-balancing.

This service is specifically for Generic VIP's/Non f5 hosted VIPs

## How to request

Please use the following base config in your application file:

```yaml

application_name:
  services:
    WideIP:
      - name: name_of_your_wideip
        dc1_server: "192.168.1.1"
        dc2_server: "192.168.1.2"
      - name: name_of_another_wideip
        dc1_server: "192.168.2.1"
        dc2_server: "192.168.2.2"

```

Please note:
* the NAME will form your WideIP host record
* dc1 and dc2 ip's are required for the generic VIP/Server setup, other Services are available for auto-detected VIPs that will not require this input.


## Modification/Deletion

To modify or delete any instance of this service please just either remove from your application file or delete the relevant section of the yaml related to that ServiceItem. 

