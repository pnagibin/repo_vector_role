



# Home
  
---
## Role Name
  
repo_vector_role  
  
---
## Description
  
Дання роль устанавливает на целевую машину сервис Vector  
  
---
## Dependencies
  
None  
  
---
## Information
  

|Author|Company|License|Minimum Ansible Version|
| :---: | :---: | :---: | :---: |
|Nagibin Pavel|None|license (BSD, MIT)|2.1|

# TASKS


# main.yml


* Vector | Install package

* Vector | Configure vector

* Vector | Configure services





# install_yum.yml


* Install Vector | YUM install





# configure_service.yml


* Configure Service | Template systemd unit





# configure_service.yml


* Configure Service | Template systemd unit

# Template





# vector.service.j2
  
---  
```

[Unit]
Description=Vector Service
After=network.target
Requires=network-online.target
[Service]
User={{ ansible_user_id }}
Group={{ ansible_user_gid }}
ExecStart=/usr/bin/vector --config-yaml {{ vector_config_dir }}/vector.yml --watch-config true
Restart=always
WantedBy=multi-user.target%  
```

# Default





# main.yml
  
---
## vector_version
  
```

0.33.0
...
  
```
## vector_config_dir
  
```

'{{ ansible_user_dir }}/vector_config'
  
```
## vector_config
  
```

null
...
  
```