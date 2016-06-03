unitedtraders.sonarqube
=========

Sonar is a source-code quality tool.

Requirements
------------

Sonar can use either a MySQL variant, or PostgreSQL, as a database. You should select just one of these using the features.

    features:
      mysql: True
      postgresql: False

Databases and database users should be created before this role.

Java should be installed before this role.

Role Variables
--------------

`defaults/main.yml` contain variables. Please change the sonar_password first. For advanced users the sonar_plugins might be interesting.

Dependencies
------------

Role has no dependencies.

Example Usage
----------------

```
- hosts: sonarqube
  name: SonarQube server
  become: true
  roles:
    - role: ansiblebit.oracle-java
      oracle_java_set_as_default: yes
    - role: anxs.postgresql
      postgresql_timezone: 'Europe/Moscow'
      postgresql_users:
        - name: sonar
          password: sonar
      postgresql_databases:
        - name: sonar
          owner: sonar
    - role: unitedtraders.sonarqube
```

License
-------

BSD

Author Information
------------------

Bas Meijer (@bbaassssiiee)
Alik Kurdyukov
