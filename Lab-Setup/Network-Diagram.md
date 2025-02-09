# 🔒 Diagrama de Red del Laboratorio Blue Team

```mermaid
graph LR
    subgraph Red Aislada [🔗 Red Interna (VirtualBox)]
        direction LR
        A[Kali Linux] --> B[Windows 10]
        A --> C[Ubuntu Server]
        C --> D[Splunk]
        C --> E[Suricata]
        C --> F[Wireshark]
    end

    style A fill:#ff9999,stroke:#333,stroke-width:2px    <!-- Color para el atacante -->
    style B fill:#99ccff,stroke:#333,stroke-width:2px    <!-- Color para el endpoint -->
    style C fill:#99ff99,stroke:#333,stroke-width:2px    <!-- Color para el servidor de seguridad -->
