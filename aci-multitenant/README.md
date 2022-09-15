# ACI Multitenant Example

The general idea is to have a single playbook to build/amend a given Tenant in ACI, then customer specific vars files holding info pertaining to the given customer.

Run from within the project root folder with:

ansible-playbook playbooks/build.yaml -i inventory/host.yaml -e "customer=C3AAA"

In the example above, we are running the vars file from the 'C3AAA' customer folder. Add more customer folders and vars as required.

This is being run against the Cisco DevNet 'always-on' ACI sandbox, which is an excellent free resource for testing ACI automation...

