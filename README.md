# base-vms
This repository is a set of base config files which helps you to create multi virtual machines with costume configs as soon as possible.

> [!note]
> Please consider that this is just base configs and normally for test environmets you should change default configs.

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
