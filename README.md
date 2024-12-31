# Ansible Role: admin_user

An Ansible role that creates an user with administrative profile on Linux boxes.

## 🚀 Motivation

At least one administrative user is required to manage Linux boxes. It would be nice to create this user and configure things like SSH `authorized_keys` and some `.bashrc` options automatically.

## 📑 Role Variables

Check [here][01].

## 🧰 Dependencies

None.

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Ensure admin user exists
  hosts: all
  become: true
  gather_facts: true
  vars:
    admin_user__user: admin
    admin_user__group: admin
    admin_user__ssh_authorized_keys:
      - admin
  roles:
    - fernandobohrer.admin_user
```

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][02] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][03].

[01]: defaults/main.yml
[02]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[03]: /LICENSE
