win_debloat
===========
[![Ansible Lint](https://github.com/oxivanisher/role-win_debloat/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/oxivanisher/role-win_debloat/actions/workflows/ansible-lint.yml)

Remove unwanted software which Microsoft installs by default or trough updates.

Requirements
------------

This role is built to be used with Ansible oder SSH on Windows.

Notes
-----

Check this: https://github.com/AlexNabokikh/windows-playbook/blob/master/tasks/debloat.yml
And also this: https://www.reddit.com/r/sysadmin/comments/y254xp/how_to_i_remove_apps_like_instagram_facebook_etc/
Get shit apps:
```plaintext
Get-AppxProvisionedPackage -Online | Select-Object DisplayName
Get-AppxProvisionedPackage –online | where-object {$_.packagename –like "*APP_NAME_HERE*"}
Get-AppxProvisionedPackage –online | where-object {$_.packagename –like "*APP_NAME_HERE*"} | Remove-AppxProvisionedPackage –online

# Microsoft is doing everything to push edge down the throat of everyone. I found the latest installed package like this:
Get-AppxPackage *Microsoft.MicrosoftEdge*
```

Role Variables
--------------

| Name                   | Comment                        | Default value                                        |
|------------------------|--------------------------------|------------------------------------------------------|
| win_debloat_bloatware | List of software to be removed | See the `defaults\main.yml` file, it's quiet a list. |

Example Playbook
----------------
```yaml
- name: Remove windows Bloatware
  hosts: windows
  roles:
    - role: oxivanisher.windows_desktop.win_debloat
```

License
-------

BSD

Author Information
------------------

This role is part of the [oxivanisher.windows_desktop](https://galaxy.ansible.com/ui/repo/published/oxivanisher/windows_desktop/) collection, and the source for that is located on [github](https://github.com/oxivanisher/collection-windows_desktop).
