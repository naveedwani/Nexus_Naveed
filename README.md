Sonatype Nexus
==============

An ansible role to install and configure Nexus on Linux.

Version History
---------------


| **Date** | **Version** | **Description** | **Changed By** |
| - | - | - | - |
| **20 march 2022** | 1.0 | Initial commit | Ishan Ji G |

Dependencies
------------

* Java 8/11 (64-bit)

Directory Layout
----------------

```
NEXUS

├── defaults
│   └── main.yml
├── handlers
│   └── main.yml
├── media
│   └── web.PNG
├── meta
│   └── main.yml
├── README.md
├── tasks
│   ├── install.yml
│   ├── main.yml
│   └── pre-requisite.yml
├── templates
│   ├── logback.xml.j2
│   ├── nexus-default.properties.j2
│   ├── nexus.rc.j2
│   ├── nexus.service.j2
│   └── nexus.vmoptions.j2
└── vars
    └── main.yml



7 directories, 13 files


```

Role Variables
--------------


| **Variables** | **Default Values** | **Description** |
| - | - | - |
| nexus_user | wccuser | Service user |
| nexus_group | wccuser | Service group |
| nexus_installation_dir | /opt | Installation directory |
| nexus_version | 3.22.0-02 | Nexus Version |
| nexus_data_dir | /data | Data directory |
| nexus_port | 8081 | Service port |
| nexus_min_memory | 500 | Min memory |
| nexus_max_memory | 500 | Max memory |
| nexus_direct_memory | 500 | Direct memory |
| nexus_host | 0.0.0.0 | Service Host |
| nexus_log_dir | /var/log/nexus | Log Directory |
| nexus_tmp_dir | nexus_data_dir/tmp | Tmp Directory |

Example Playbook
----------------

```
---
- hosts: server
  become: true
  roles:
    - role: nexus
...

$  ansible-playbook site.yml -i inventory

```

Inventory
---------

An inventory should look like this:-

```ini
[server]
172.xx.xxx.xxx  
```

**After the successful installation of nexus, browse through the nexus url and you would get your login page**
![login](./media/web.PNG)

#References
-----------

* **[Source Code](https://www.vogella.com/tutorials/Nexus/article.html)**

# Author

---

**[Naveed Wani](waninaveed01@gmail.com)**
