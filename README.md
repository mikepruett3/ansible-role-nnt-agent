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
beacon: false
beacon_host: "http://beacon.example.org"

software_url: "http://www.example.org"
package_name: "managesoft-17.3.0-1.x86_64.rpm"
package_version: "17.3.0"

cert_file:      "mgsft_rollout_cert"
response_file:  "mgsft_rollout_response"
```

```beacon``` **(Required)** Controls if the client install will be used with a local Beacon Server. This should be either **true** or **false** (Default is **false**).

```beacon_host``` **(Required)** The URL of the local Beacon Server. This should be either **http** or **https**.

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_name``` **(Required)** The Installer package name.

```package_version``` **(Required)** The version of the Installer package. Used in determination if Upgrading existing install.

```cert_file``` **(Required)** The name of the beacon certificate file to download from the `software_url`.

```response_file``` **(Required)** The name of the agent installaton response file to download from the `software_url`.

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
           vars:
            software_url: "http://www.example.org"
            package_name: "flexera-agent-installer"
            package_version: "17.3.0"
```

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3/ansible-role-nnt-agent)
