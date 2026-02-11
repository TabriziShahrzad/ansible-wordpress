# Role: WordPress

## Description
This Ansible role automates the installation and configuration of a complete LAMP stack (Linux, Apache, MariaDB, PHP) and WordPress CMS. It handles database creation, user setup, WordPress download, and Apache configuration.

## Prerequisites
- Target OS: Debian/Ubuntu-based Linux distributions (e.g., Ubuntu 20.04, 22.04, 24.04).
- Ansible: Version 2.9 or higher installed on the control node.
- Sudo privileges: The Ansible user on the target host must have sudo access.
- Internet connection: Required to download packages and WordPress core files.

## Role Variables
Default variables are defined in `defaults/main.yml`. You can override them in your playbook or `host_vars`.

| Variable Name | Default Value | Description |
|---------------|---------------|-------------|
| `wp_db_name` | `wordpress_db` | The name of the MySQL/MariaDB database to create. |
| `wp_db_user` | `wordpress_user` | The MySQL user to create for WordPress. |
| `wp_db_password` | `wordpress_pass` | Password for the MySQL user. |
| `apache_port` | `80` | The port Apache listens on. |
| `wordpress_download_url` | `https://wordpress.org/latest.tar.gz` | URL to download WordPress archive. |
| `wordpress_dest` | `/var/www/html/` | Directory where WordPress will be installed. |
| `wordpress_owner` | `www-data` | User that will own the WordPress files. |
| `wordpress_group` | `www-data` | Group that will own the WordPress files. |
| `php_packages` | `['php', 'php-mysql', ...]` | List of PHP extensions to install. |

## Dependencies
None. This role handles the installation of Apache, MariaDB, and PHP internally.

## Example Playbook
Including an example of how to use your role (for example, in a `site.yml` file):

```yaml
- hosts: webservers
  become: yes
  roles:
    - wordpress
```

## How to Run
To run this playbook, execute the following command from the project root directory:

```bash
ansible-playbook -i inventory playbook_worpress.yml
```


## Verification
After the playbook finishes successfully:

Open your web browser.
Navigate to http://<server_ip>.
You should see the WordPress language selection page.
License
MIT

## Author Information
This role was created in 2026 by [Shahrzad Ghorbani].
