# ansible-vikunja

The entire setup is managed via ansible. If possible please do not manually interfere with this setup.

[Vikunja](https://kolaente.dev/vikunja/) is a task management software for teams.

## Usage (on ansible operators side)
* Copy the example files over to their intended location `cp example-hosts hosts && cp vars/example-default.yml vars/default.yml`
* Edit the contents of `hosts` to include the IP address of your host(s)
* Edit the contents of `vars/default.yml` to replace the database passwords with your own, secure passwords
* Encrypt the password values in `vars/default.yml` with [ansible vault](https://docs.ansible.com/ansible/latest/user_guide/vault.html)
* Run `ansible-galaxy install bobbyrenwick.pip` to install required external roles
* Run `ansible-playbook -i hosts setup.yml` to configure your host(s)

## Usage (on this server)
* To manually start the service run `docker-compose up -d`

## Data directories (found on host after first run)
* `db` contains the persistent mariadb data
* `files` contains all other files

## Variables used to create the configuration on this server 

* `mariadb_root_password`: Root password of the database server 
* `mariadb_user`: Username of your desired application-specific database user
* `mariadb_user_password`: Password of your application-specific database user
* `mariadb_db_name`: Database name of your application-specific database
