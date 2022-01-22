inv_report
=========

An HTML based report to target Cisco based network devices and facts, using the `cisco.ios.ios` collection.  HTML markup is generated from a series of `Jinja2` templates, and styled with the `UIkit`, and `FontAwesome` CSS frameworks, via their `CDN` links for portability.

For more information about the libraries used, or to further customize the output for your needs:

[UIkit](https://getuikit.com/)
- A lightweight `CSS` framework, providing a clean, modern, and responsive design.

[Font Awesome](https://fontawesome.com/)
- A collection of `icons`, and `glyphs` to spice up your UI.

NOTE:
You should consider downloading the `CSS` files locally for a more deterministic behavior in a Production use case, or for viewing the output offline.
>Simply swap out the `CDN` links for the paths to the local copies in the `css.j2` template.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

| Variable | Defaults | Type | Comments | Source |
|-|-|-|-|-|
| `report_name` | Ansible Inventory Report | `str` | This is the **default** title displayed on the report, located in the `card title` markup in `layout.j2`. | Role Defaults |
| `file_path` | /var/www/html/index.html | `str` | This is the **default** file `path` where the report will be created. | Role Defaults |
| `table_type` | std_table | `str` | This is the **default** table template, optionally select the `condtional_table` for conditional based highlighting of table data, or feel free to create your own following the pattern in the included templates. | Role Defaults |

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

- `cisco.ios.ios`

You can install the Cisco IOS collection with the Ansible Galaxy CLI:

    ansible-galaxy collection install cisco.ios

You can also include it in a `requirements.yml` file and install it with `ansible-galaxy collection install -r requirements.yml`, using the format:

```yaml
---
collections:
  - name: cisco.ios
```
## Using this collection

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- hosts: all
  gather_facts: False
  tasks:
    - name: fetch facts about the host
      cisco.ios.ios_facts:
        gather_subset:
          - min

    - name: call the role to generate the report
      import_role:
        name: inv_report
      vars:
        file_path: ./inventory_report_ios.html
```

License
-------

Apache-2.0

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
