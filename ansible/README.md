# Generate final_list.yaml in the first place
ansible-playbook main.yaml --vault-password-file generate_final_list.yaml 

# Run just qr_codes
ansible-playbook main.yaml --vault-password-file ../../ansible_vault --skip-tags org_graphite --skip-tags org_counter

# Run just organizations without qr codegenerator
ansible-playbook main.yaml --vault-password-file ../../ansible_vault -t org_graphite -t org_counter
