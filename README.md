# Ansible Ubuntu Wordpress

This Ansible playbook sets up an Ubuntu 20.04 box for super-fast Wordpress hosting.

It includes:

 - Configuring Ubuntu with auto updates
 - Nginx, with page caching to local ram storage
 - phpfpm for PHP
 - MariaDB for a database
 - Redis for object caching
 - Certbot & LetsEncrypt for SSL.

Additionally, it'll:

 - Install a list of Wordpress plugins
 - Install a list of themes, including activating one if you want it to
 - Import a database export from another site

## Pre-requisites

- An Ubuntu 20.04 box
- Ansible

## Installation

1. Create your own inventory: `cp -rfp inventories/sample inventories/my-cool-website`

2. Review `group_vars/all.yml`. Change settings by overriding them in `inventories/my-cool-website/group_vars/all.yml`.

3. Update `inventories/my-cool-website/inventory` with your host's IP address.

4. Install the dependent roles and collections: `ansible-galaxy install -r requirements.yml`

5. Run it: `ansible-playbook -i inventories/my-cool-website/inventory setup.yml -b`