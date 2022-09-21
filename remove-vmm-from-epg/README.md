# Remove VMM from EPGs

We had a situation where we deleted an obsolete VMM domain from the APIC GUI, only to find it didn't delete the relationships to the 450 EPGs that were using it....super annoying! This little playbook was written to enable us to remove the 'missing-targets' en-masse using a CSV as the EPG data source.

This example is being run against the Cisco DevNet 'always-on' ACI sandbox:
https://sandboxapicdc.cisco.com

The playbook has user interactive APIC username/password which for the sandbox is admin/!v3G@!4@Y

Amend the CSV to match your use-case and run from within the project root folder with:

```ansible-playbook remove-vmm-from-epg.yaml```

This approach could just as easily be used to add a VMM to multiple EPGs (change 'state' to 'present') or the for adding/removing Physical Domains. See module [documentation](https://docs.ansible.com/ansible/latest/collections/cisco/aci/aci_epg_to_domain_module.html#ansible-collections-cisco-aci-aci-epg-to-domain-module)



