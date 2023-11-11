# MOVED TO CODEBERG - [codeberg.org/chdorner/bookwyrm-infra](https://codeberg.org/chdorner/bookwyrm-infra)

# An opinionated BookWyrm setup

## Background

> I've been running my own BookWyrm instance for some time now, mainly as a means to get operating and admin experience while contributing to the development of the project. BookWyrm is a social reading and reviewing application, a sort of federated GoodReads alternative which is interoperable with other ActivityPub software like Mastodon.

More in [this post on amble.blog](https://amble.blog/2022/12/30/an-opinionated-guide-to-operating-bookwyrm/).

## Setup

1. Copy the `inventory.example.yaml` and set your host and user
2. If your SSH user requires a password to get sudo access, create a `.become-password` file and paste in the password
3. Copy the `secret.example.yaml` and fill out all the values
4. Copy the `vars.example.yaml` and fill out all the values

Highly recommended: Use [ansible-vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html) to encrypt your `secret.yaml`.

## Applying changes

```
ansible-playbook -i inventory.yaml \
  --become-password-file .become-password \
  --vault-password-file .vault-password \
  playbook.yaml
```
