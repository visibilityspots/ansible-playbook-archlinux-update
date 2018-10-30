# ansible-playbook archlinux update

this playbook can be used to update mulitple archlinux systems based on the [pacman helper](https://docs.ansible.com/ansible/latest/modules/pacman_module.html) and the [aur module](https://github.com/kewlfft/ansible-aur)

It will by default install [yay](https://github.com/Jguer/yay) on your system by using makepkg toghether with an aurman user which will be used to upgrade the systems.

## configuration

you'll have to create a vault file which contains your passwords per host as described in the hosts inventory file.

```
$ ansible-vault create vault
New Vault password:
Confirm New Vault password:
 [WARNING]:  does not exist, creating...
su_password_localhost: THE-SUDO-PASSWORD
```

## usage

$ ansible-playbook -i hosts --diff update.yml --vault-password-file=.vault_pass
