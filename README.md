# linuxserver_to_domain
This is an Ansible playbook that adds a Linux server to an existing Active Directory Domain so users can be authorized from the Active Directory group membership.
To use this, first you have to creare a vault using the following command:

annsible-vault create vault_name.vault and add a password to it.

a more secure way to do it is to use the command:

ansible-vault create FILENAME --vault-password-file PASSWORDFILE

PASSWORDFILE is a simple text file with the passsword of the vault. This way yo know you wont' loose it.

After that, make sure your hosts file has a similar structure as the one in the repository.

Then, you'll execute the playbook using the following command:

ansible-playbook -i [path/to/hostsfile] [path/to/playbookfile] -e@./[path/to/vaultfile]  --vault-password-file ~/[path/to/passwordfile]
