# Ansible Role: os-common
Ansible role to configure Linux OS (Security, prerequisite packages and tools, etc ...)


This role :  :
  -  Install and configures Essentiels Extra Repositories (epel, powertools)
  -  Install useful packages or sysadmin tools
  -  Create base environement for systeme and infra administrators (users, directories, etc ...)
  -  Create base environement for applications and servicies


## Requirements

None.

## Role Variables

vailable variables are listed below, along with default values (see `defaults/main.yml`):

### os_app_directories

Use `os_app_directories` to define needed applications direcories

```
os_app_directories:
  - Name: "Application root directory"
    path: /app
    mode: '0755'
```

### os_infra_directories

Use `os_infra_directories` to define needed applications direcories

```
os_infra_directories:
  - Name: "Infra tools root Directory"
    path: /app/infra
    mode: '0755'
  - Name: "Test root Directory"
    path: /app/test
    mode: '0755'
```

## Dependencies

None.

## Example Playbook

    - hosts: server
      roles:
        - { role: shmii.os-common }


## Warning / known bugs

/!\ pour l'utilisation de molecule depuis WSL/WSL2 il faut creer le dossier `/sys/fs/cgroup/systemd` sur le sous systeme linux hote.
`sudo mkdir /sys/fs/cgroup/systemd`
celui ci est nessesaire pour certains os (RHEL9, Rocky9, etc ...)

## License

GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007

## Author Information

This role was created in 2022 by [Thomas CHALMEL] (https://www.thomas.chalmel.org/).
