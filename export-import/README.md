sudo resolvectl domain crc ~testing;
sudo resolvectl dns crc 192.168.130.11;
sudo resolvectl llmnr crc yes


ansible-navigator run playbook_export_import_transform.yaml -i inventory -m stdout --eei localhost/ansible-execution-env --vault-password-file ../../../.vault_password

ansible-playbook playbook_jobtemplate_export_import_transform.yaml --vault-password-file ../../../.vault_password

ansible-playbook playbook_workflow_export_import_transform.yaml --vault-password-file ../../../.vault_password