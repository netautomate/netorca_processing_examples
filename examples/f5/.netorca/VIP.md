# VIP Service

This will create a basic HTTPS VIP service

## How to request

Please use the following base config in your application file:

```yaml

application_name:
  services:
    VIP:
      - name: name_of_your_vip
        target_ips:
          - "192.168.1.1"
          - "192.168.1.2"
      - name: name_of_another_vip
        target_ips: 
          - "192.168.2.1" 
          - "192.168.2.2"

```



## Modification/Deletion

To modify or delete any instance of this service please just either remove from your application file or delete the relevant section of the yaml related to that ServiceItem. 

