Batutah Postgresql
=========

Ansible role for install postgresql 13 on Ubuntu 20.04

## Vars

```yml
postgresql_hba_entries:
  - {type: local, database: all, user: postgres, auth_method: peer}
  - {type: local, database: all, user: all, auth_method: peer}
  - {type: host, database: all, user: all, address: '127.0.0.1/32', auth_method: md5}
  - {type: host, database: all, user: all, address: '::1/128', auth_method: md5}

postgresql_global_config_options:
  - option: listen_addresses
    value: '*'

postgres_users_no_log: true

postgresql_databases:
  - name: exampledb # required; the rest are optional
    lc_collate: # defaults to 'en_US.UTF-8'
    lc_ctype: # defaults to 'en_US.UTF-8'
    encoding: # defaults to 'UTF-8'
    template: # defaults to 'template0'
    login_host: # defaults to 'localhost'
    login_password: # defaults to not set
    login_user: # defaults to 'postgresql_user'
    login_unix_socket: # defaults to 1st of postgresql_unix_socket_directories
    port: # defaults to not set
    owner: # defaults to postgresql_user
    state: # defaults to 'present'

postgresql_users:
  - name: jdoe #required; the rest are optional
    password: # defaults to not set
    encrypted: # defaults to not set
    priv: # defaults to not set
    role_attr_flags: # defaults to not set
    db: # defaults to not set
    login_host: # defaults to 'localhost'
    login_password: # defaults to not set
    login_user: # defaults to '{{ postgresql_user }}'
    login_unix_socket: # defaults to 1st of postgresql_unix_socket_directories
    port: # defaults to not set
    state: # defaults to 'present'

```

## References

- https://wiki.postgresql.org/wiki/Apt
- https://github.com/geerlingguy/ansible-role-postgresql


&copy; 2021 - Andi Susanto