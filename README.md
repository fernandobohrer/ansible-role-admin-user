# Ansible Role: adminuser

An Ansible role that creates an user with administrative profile on Linux boxes.

## 🚀 Motivation

At least one administrative user is required to manage Linux boxes. It would be nice to create this user and configure things like SSH `authorized_keys` and some `.bashrc` options automatically.

## 📑 Role Variables

Check `defaults/main.yml`.

## 🧰 Dependencies

None.

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Deploy adminuser
  hosts: all
  become: true
  gather_facts: true
  vars:
    admin_user: admin
    admin_group: admin
    authorized_ssh_keys:
      - admin
  roles:
    - fernandobohrer.adminuser
```

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][01] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][02].

[01]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[02]: /LICENSE
