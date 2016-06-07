# ansible-role-simple-harden

## WARNING: Not fully tested. Use or apply only to test systems.

### Role to apply some simple hardening configurations

The [Security Content Automation Protocol (SCAP)](http://scap.nist.gov/) is a U.S. standard maintained by the National Institute of Standards and Technology (NIST). SCAP provides a specification for system for vulnerability detetection and remediation.

SCAP supports the process of FISMA Compliance, and the [National Vulnerability Database (NVD)](http://nvd.nist.gov/) is the U.S. government content repository for SCAP.

This role applies basic configuration updates for Kernel networking and the Audit, SSH and Firewall daemons to satisfy a number of STIG rules that fail out-of-the-box for Red Hat Enterprise and CentOS GNU/Linux version 7 distributions.

### To apply these rules to your server

Example `simple-harden.yml`:
```
- name: Harden all servers
  hosts: servers
  roles:
    - { role: CivicActions.simple-harden, become: true }
```

Run command:
```
ansible-playbook -i inventory simple-harden.yml
```
