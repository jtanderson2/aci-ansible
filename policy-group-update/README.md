# Policy Group Update

This playbook is used to bulk update Interface Policy Groups. 

In this example we're adding 'Spanning Tree Interface' and 'Storm Control' policies to a number of Policy Groups defined in a CSV (it is assumed the interface polices exist). 

This could just as easily be used to update other policies within the Policy Groups; see module [documentation](https://docs.ansible.com/ansible/latest/collections/cisco/aci/aci_interface_policy_leaf_policy_group_module.html#ansible-collections-cisco-aci-aci-interface-policy-leaf-policy-group-module)

This is being run against the Cisco DevNet 'always-on' ACI sandbox: https://sandboxapicdc.cisco.com

The playbook has user interactive APIC username/password which for the sandbox is admin/!v3G@!4@Y

Amend the CSV and playbook to match your use-case and run from within the project root folder with:

```ansible-playbook policy-group-update.yaml```

Note, this will create the Policy Groups defined in CSV if they don't exsit already, so the approach can be also be used for initial deployment purposes.
