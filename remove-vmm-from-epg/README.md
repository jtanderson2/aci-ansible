# Remove VMM from EPGs

When you delete an obsolete VMM domain from the APIC, it doesn't delete the relationships to the EPGs that were using it....and that could be 100s of EPGs, hence would be super tedious having to delete those relationships manually! This little playbook was written to remove the 'missing-targets' en-masse using a CSV as the EPG data source.

This example is being run against the Cisco DevNet 'always-on' ACI sandbox:
https://sandboxapicdc.cisco.com

The playbook has user interactive APIC username/password which for the sandbox is admin/!v3G@!4@Y

Amend the CSV to match your use-case and run from within the project root folder with:

```ansible-playbook remove-vmm-from-epg.yaml```

You can find all the EPGs associate with a given VMM using the following moquery command from the APIC CLI; it then needs parsing into CSV format ;)

```moquery -c fvAEPg -x query-target=children | grep OLDVMM | grep dn | grep -v rtinfraFuncToEpg```

This approach could just as easily be used to add a VMM to multiple EPGs (change 'state' to 'present') or the for adding/removing Physical Domains. See module [documentation](https://docs.ansible.com/ansible/latest/collections/cisco/aci/aci_epg_to_domain_module.html#ansible-collections-cisco-aci-aci-epg-to-domain-module)



