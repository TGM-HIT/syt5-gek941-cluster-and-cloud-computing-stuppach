# SYT GK941 Cluster- und Cloud-Computing 
### "Container mit Kubernetes" 

**Authors:** Stuppig Markus 5DHIT, Wallpach Melissa 5BHIT
**Version:** 2024-11-14

## Fragestellungen 
### Unterschiede zwischen klassischen VMs und Containern

- **Ressourcennutzung**: VMs virtualisieren die gesamte Hardware und benötigen ein vollständiges Betriebssystem. Container teilen sich dagegen das Host-Betriebssystem und sind dadurch deutlich ressourcenschonender.

- **Isolierung**: VMs bieten eine stärkere Isolierung, da sie komplett voneinander getrennt sind. Container teilen sich den Kernel des Host-Systems, sind aber auf Prozessebene isoliert.

- **Startzeit**: Container starten in Sekunden, während VMs mehrere Minuten zum Booten benötigen können.

- **Portabilität**: Container sind hochportabel und können problemlos zwischen verschiedenen Umgebungen verschoben werden. VMs sind stärker an die zugrunde liegende Infrastruktur gebunden.

- **Skalierbarkeit**: Container lassen sich sehr schnell und effizient skalieren. Das Skalieren von VMs ist aufwendiger.
