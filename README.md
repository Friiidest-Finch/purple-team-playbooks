# Purple Team Playbooks

Kumpulan playbook yang menghubungkan **teknik serangan** dengan **deteksi** dan **perbaikan**.
Setiap playbook mengikuti alur: *Simulasi → Telemetri → Deteksi → Gap → Remediasi*.

## Struktur Repo

```
purple-team-playbooks/
├── README.md
├── LICENSE                  # MIT
├── playbooks/
│   └── T1059.001-powershell.md
├── detections/
│   └── sigma/
│       └── proc_creation_win_powershell_encoded_command.yml
├── template/
│   └── playbook-template.md
└── docs/
    └── lab-setup.md         # Sysmon, Wazuh/Splunk, Windows VM
```

## Daftar Playbook

| ATT&CK | Teknik | Status | Deteksi |
|--------|--------|--------|---------|
| T1059.001 | PowerShell | ✅ Draft | Sigma |
| T1003.001 | LSASS Memory | ⬜ Rencana | - |
| T1053.005 | Scheduled Task | ⬜ Rencana | - |
| T1547.001 | Registry Run Keys | ⬜ Rencana | - |
| T1021.002 | SMB / Admin Shares | ⬜ Rencana | - |

## Template Playbook

Setiap file di `playbooks/` berisi:
1. **Ringkasan teknik** (ID ATT&CK, taktik, platform)
2. **Simulasi** (referensi test Atomic Red Team, jalankan hanya di lab)
3. **Telemetri yang diharapkan** (Event ID / log source)
4. **Deteksi** (link ke rule Sigma + query SIEM)
5. **Hasil uji** (terdeteksi / tidak, false positive)
6. **Remediasi & hardening**

## Lab yang Dipakai
- Windows 10/11 VM + Sysmon (config SwiftOnSecurity / Olaf Hartong)
- Wazuh atau Splunk/ELK sebagai SIEM
- Atomic Red Team untuk emulasi

## Lisensi
MIT
