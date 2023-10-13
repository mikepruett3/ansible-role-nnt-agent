Ansible Role: New Net Technologies Change Tracker Agent (Gen7)
=========

Ansible role to install/uninstall New Net Technologies Change Tracker Agent (Gen7) on Linux servers.

Requirements
------------

The role does not require anything to run on Ubuntu, Debian or RHEL and its derivatives. This role assumes that you have the software package located on a web server somewhere in your environment.

Role Variables
--------------

Available variables are listed below, along with default values (see ```defaults/main.yml```):

``` yaml
proxy: False
proxy_host: "myproxyserver.example.com"
proxy_port: "3128"
proxy_protocol: "http"

hub_host: "nnt.example.org"
hub_ip: '1.2.3.4'
hub_url: "https://nnt.example.org/api"
agent_username: "agent"
agent_password: "password"

software_url: "http://www.example.org"
package_name: "managesoft-17.3.0-1.x86_64.rpm"
package_version: "17.3.0"
```

```proxy``` **(Required)** Controls if the client install will be used with a HTTP/HTTPS Proxy Server. This should be either **True** or **False** (Default is **False**).

```proxy_host:``` **(Required)** Hostname or IP Address of the Proxy Server to use. Settings only required when ```proxy``` is set to **True**.

```proxy_port:``` **(Required)** Port to use to connect with the Proxy Server. Settings only required when ```proxy``` is set to **True**.

```proxy_protocol``` **(Required)** Protocol to use to connect with the Proxy Server. This should be either **http** or **https**. Settings only required when ```proxy``` is set to **True**.

```hub_host``` **(Required)** Hostname of the Hub Server.

```hub_ip``` **(Required)** IP Address of the Hub Server.

```hub_url``` **(Required)** Url to the Hub Server.

```agent_username``` **(Required)** Username for the Hub Server.

```agent_password``` **(Required)** Password for to the Hub Server.

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_name``` **(Required)** The Installer package name.

```package_version``` **(Required)** The version of the Installer package. Used in determination if Upgrading existing install.

Role variables can be stored with the ```hosts.yaml``` file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

``` yaml
    - hosts: servers
      roles:
         - role: mikepruett3.nnt-agent
```

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3/ansible-role-nnt-agent)
