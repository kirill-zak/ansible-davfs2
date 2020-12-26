Role Name
=========

Install and configurate davfs

Requirements
------------

N/A

Role Variables
------------

* `davfs2_users`: List of users who will be added to the `davfs2` group
* `davfs2_mounts`: List of WebDAV mounts

The structure of WebDAV mount item:
* `name`: Name of point.
* `src`: WebDAV url. Example `https://webdav.mycloud.local`.
* `login`: WebDAV login.
* `password`: WebDAV password.
* `mount_path`: Local mount path

Dependencies
------------

- Python

Example Playbook
----------------

```yaml
    - hosts: servers
      vars:
        davfs2_users: 
          - dummy
        davfs2_mounts:
          - name: MyCloud
            src: https://webdav.mycloud.local
            login: dummy
            password: pa$$Word
            mount_path: /media/cloud/MyCloud
      roles:
         - { role: kirill_zak.ansible_davfs2 }
```

License
-------

MIT

Author Information
------------------

https://kirill-zak.ru
