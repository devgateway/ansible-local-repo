local-repo
=========

Adding a local YUM repository and GPG keys

Requirements
------------

YUM package manager. DNF support is still to-do.

Role Variables
--------------

### rpm\_gpg\_keys

List of GPG public key files (basenames in files subdirectory) to install and import.

### localrepo\_baseurl

**List, not string,** of base URLs supported by YUM.

### localrepo\_ignore\_proxy

Boolean, defaults to True. Force ignore YUM proxy settings, and use direct connection.

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
      - role: local-repo
        rpm_gpg_keys:
          - RPM-GPG-KEY-admin
        localrepo_baseurl:
          - https://yum.example.org/scientific/{{ ansible_distribution_major_version }}/

License
-------

GPLv3+

Author Information
------------------

Development Gateway
