# Ansible Role: pihole

An opinionated Ansible role that deploys and configures the [Pi-hole][01] ad blocker.

## 🚀 Motivation

Pi-hole is a network-wide ad blocking solution. The main advantages of using this solution are listed in Pi-hole's [website][01]:

```text
- Instead of browser plugins or other software on each computer, install Pi-hole in one place and your entire network is protected.

- Network-level blocking allows you to block ads in non-traditional places such as mobile apps and smart TVs, regardless of hardware or OS.

- Since advertisements are blocked before they are downloaded, network performance is improved and will feel faster.
```

This role deploys [Pi-hole][01] and its dependencies and configures the solution to block ads on your network.

## 📑 Role Variables

Check [here][02].

## 🧰 Dependencies

Check [here][03].

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Deploy Pi-hole
  hosts: all
  become: true
  gather_facts: true
  roles:
    - fernandobohrer.pihole
```

## 📋 Usage

Once the deployment process is complete, you will need to configure your router to have DHCP clients use Pi-hole as their DNS server which ensures all devices connected to your network will have content blocked without any further intervention. Details can be found [here][04] and [here][05].

## ℹ️ Additional information

Please note that this role makes use of the lists that are bulleted with a ✔️ and displayed in green available at [firebog.net][06].

As can be seen from [here][07], these ticked lists are meant to be used with Pi-hole installations that will have minimal maintenance.

Since the main goal of this role is to automate the deployment of Pi-hole in a way that the solution does not stand in your way, it makes sense to use lists that are less likely to break things.

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][08] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][09].

[01]: https://pi-hole.net/
[02]: defaults/main.yml
[03]: meta/main.yml
[04]: https://docs.pi-hole.net/main/post-install/
[05]: https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245
[06]: https://firebog.net/
[07]: https://v.firebog.net/hosts/lists.php
[08]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[09]: /LICENSE
