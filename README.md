Role Name
=========

A brief description of the role goes here.

Notes
-----

Check this: https://github.com/AlexNabokikh/windows-playbook/blob/master/tasks/debloat.yml
And also this: https://www.reddit.com/r/sysadmin/comments/y254xp/how_to_i_remove_apps_like_instagram_facebook_etc/
Get shit apps:
```plaintext
Get-AppxProvisionedPackage -Online | Select-Object DisplayName
Get-AppxProvisionedPackage –online | where-object {$_.packagename –like "*APP_NAME_HERE*"}
Get-AppxProvisionedPackage –online | where-object {$_.packagename –like "*APP_NAME_HERE*"} | Remove-AppxProvisionedPackage –online
```

This is also interesting: https://superuser.com/questions/1740015/disney-just-got-installed-without-my-permission

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
