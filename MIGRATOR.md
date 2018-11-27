migrator.yml
============
Playbook for KVM guests migration (with shutdown)
## Data structure
```yaml
migrate_domains:
  - src: source_host # mandatory
    dest: destination_host # mandatory
    dest_ip: destination_host_ipv4 # optional
    vg: vg_name_on_destination # mandatory
    domains:
      - name: guest_name # mandatory
        lv: "/dev/vg/lv" # optional; set if lv is encrypted with LUKS
        ip: guest_ipv4 # optional; set if `Windows' or if qemu-ga is not running
        skip: bool # default: false
        keep_lv: bool # don't remove source LV after migration; default: false
```
