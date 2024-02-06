# base-vms
This repository contains basic configuration files that can assist you in swiftly creating multiple virtual machines with personalized settings.

> [!warning]
> Please keep in mind that these are only basic configurations, and for testing environments, it is advisable to modify the default settings.

## How to use
Set vagrant default provider as a environmet variable:
For virtualbox:
```bash
export VAGRANT_DEFAULT_PROVIDER=virtualbox
```
For libvirt:
```bash
export VAGRANT_DEFAULT_PROVIDER=libvirt
```

### Change Configs
use `vars.yaml`

to add more virtual machines, repeat this format under `VMS` block:
```yaml
  - prefix: "vm-name"
    count: <number of vms>
    box: "<vagrant box name"
    cpu: <number of cpus>
    ram: <memory in MB>
```
