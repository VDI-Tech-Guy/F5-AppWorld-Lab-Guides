---
title: "Use Case 00: Backup and Restore Role"
nd-subtitle: 
layout: "default"
weight: 1
toc: true
nd-landing-page: false
---

## Overview

This is a great example of best practices when doing major configurations with a BIG-IP. Having a backup of your previous configuration ensures that you can return to a point in time that was a known working configuration if something were to break.

`Backup-Role.yaml` is a templated Ansible play that utilizes an underlying Role that demonstrates the ability to backup a BIG-IP Configuration to a UCS File then download that UCS file to `/tmp/Use-Case-00-backup.ucs` on the local ansible box. This ensures a backup within the BIG-IP and a backup local to your machine.

`Restore-Role.yaml` is a templated Ansible play that utilizes an underlying Role that demonstrates the ability to restore a BIG-IP Configuration with the locally stored UCS File in `/tmp/Use-Case-00-backup.ucs`. This play has a check to ensure that the UCS file exists before it can run a restore.

{{< important >}}
The restore command will produce an error in some builds of Ansible even though the restoration does complete. It is a known issue due to the reset of the RestAPI services.
{{< /important >}}

## Highlights

1. Always create a backup of your environment before automating. This ensures a safe and reliable way to revert in case of any issues.

2. The Backup will actually create **two (2) backups**:  
   - One on the F5 device (located in the archives)  
   - One located in the `/f5/code-output/` directory on the Ansible node, named `hostname-date-timestamp.ucs`  
   This provides 2 levels of backup.

## Examining the Code

1. In VSCode (Code-Server) on the left menus, expand: 

`f5-bd-ansible-labs --> 401-F5-AppWorld-Lab --> Modules --> 00-Backup-Restore Role`

and select the `Backup-Role.yaml` file.

2. Notice that this playbook uses **Ansible Roles** rather than a single large playbook. Roles are used to break down code into reusable functions. In this case:  
- First, it removes AS3 from the F5 device using the `f5_remove_as3_backup` role  
- Then it uses the `f5_backup_data` role to backup the F5 device

```yaml
---
- hosts: lb
  connection: local
  gather_facts: false
  vars_files:
    - vars/f5_vars.yml
  roles:
    - f5_remove_as3_backup
    - f5_backup_data

