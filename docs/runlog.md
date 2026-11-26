# Lab run log

One line per change, newest first. Result = what the PLAY RECAP showed.

| Date | Change | Playbook | Hosts | Result | Notes |
| --- | --- | --- | --- | --- | --- |
| 2026-11-25 | OpenSCAP CIS L1 baseline scan | openscap_scan.yml | lab | webnode 76.22% (152 pass / 107 fail, 4 high) | reports kept out of git |
| 2026-11-25 | Converted Apache to role, fixed handler chain | web.yml | webnode, backupnode | check changed=0 | handlers now use listen |
| 2026-11-25 | Firewall tasks moved into roles/firewall | security.yml | lab | check: changed=0 | First role; roles_path added to ansible.cfg |
| 2026-11-25 | Added firewall/selinux tags | security.yml | lab | check: changed=0 | `--tags selinux` runs only SELinux tasks |
| 2026-11-25 | Added tags (apache, apache_config, ...) | web.yml | web | check: changed=0 | `--tags apache_config` verified |
| 2026-11-25 | Rolling updates with `serial: 1` | web.yml | web | check: changed=0 | webnode finishes before backupnode starts |
| 2026-11-25 | Split long firewall line (lint) | zabbix_windowsetup1.yml | windows | check: changed=0 | lint: production profile |
| 2026-11-25 | systemd reload moved to a handler (lint) | zabbix_setup1.yml | monitoring, lab | check: changed=0 | lint: production profile |
| 2026-11-25 | Removed truncated duplicate zabbix_setup.yml | - | - | - | zabbix_setup1.yml is the single source |
| 2026-11-25 | FQCN + comma fixes (lint) | users.yml, ad_users.yml | - | lint: 0 failures | - |
| 2026-11-25 | Installed ansible-lint 6.22.2 in a venv | - | controlnode | - | venv keeps main Ansible at 2.15.13 |
| 2026-11-25 | Tailscale offline on DC after host reboot | - | dc-homelab | fixed | Restarted Tailscale; disable key expiry for servers |
| 2026-11-24 | httpd auto-restart on failed start | zabbix_setup1.yml | zabbixnode | changed=2 | httpd had timed out at boot after the VM move |
