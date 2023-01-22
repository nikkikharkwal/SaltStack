# SaltStack

+ Salt sometimes referred to as SaltStack.
+ Open - Source Software.
+ **Used For** : for remote task execution, automation and configuration management.
+ It remotely executes commands across multiple/all machines.
+ Salt uses the Master-Client model.


### How will you deploy a file to a minion with the accession of other minions?
``` /etc/my__super/secret_file::
file. managed::
– mode:: 600
– group:: secret
– user:: secret
– contents__pillar::secret__files::my__super__secret__file 
```


### Can SaltStack support the backing up of managed files?
> Yes, SaltStack can support backing up managed files.

### How can you proceed with the Minion upgrade without restarting automatically?
 >  {%- if grains[family] == 'Debian' %} 
 
> Disable the starting services –
``` file.managed:
- name/usrsbin/policy-rc.d
- group: / root
- user: root
- mode/0755
-- '#!/bin/sh'
-- exit 101
- contents:
```

>  If already exists, then do not touch 

``` - prereq:
- replace: False
  {%- endif %}
 - pkg: Upgrade the Salt Minion
 ```

 > Upgrade the Salt Minion –
 ``` pkg.installed –
- version: 2016.11.3{% if grains['os_family'] 'Debian'}ds-1{% endif %}
  --name: salt-minion
- order: the last 
```

> Enable the Salt Minion –
``` - name: salt-minion
service.enabled:
  - pkg –Upgrade the Salt Minion
s  - require:
{%- if grains['os_family'] - 'Debian' %} 
```

> Enable the starting services:
``` - name: /usr/sbin/policy-_rc.d
file.absent:
  - pkg-Upgradethe Salt Minion
 - onchanges:
{%- endif %} 
```


### If you find a bug in Salt, then what would you do?
> Both the mailing list of the salt users and the IRC channel of salt are helpful resources. This is because they have the capability of confirming issues as well as troubleshoots to resolve their respective problems. When you find a bug in Salt, you would have to follow the particular instructions and report the bug.

### On the Firewall option, what port are you supposed to open?
> The Minions are to be connected to Master on TCP ports 4506 as well as 4505. They don’t actually need any inbound port open.
