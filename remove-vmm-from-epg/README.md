# Remove VMM from EPGs

We had a situation where we deleted an obsolete VMM domain from the APIC GUI, only to find it didn't delete the relationships to the 450 EPGs that were using it....super annoying! This little playbook was written to enable us to remove the 'missing-targets' en-masse using a CSV as the EPG data source.

This is being run against the Cisco DevNet 'always-on' ACI sandbox, which is an excellent free resource for testing ACI automation. This playbook has user interactive APIC username/password which for the sandbox is admin/!v3G@!4@Y

Amend the CSV to match your use-case and run from within the project root folder with:

```ansible-playbook remove-vmm-from-epg.yaml```

This approach could just as easily be used to add a VMM to multiple EPGs (change 'state' to 'present') or the for adding/removing Physical Domains



