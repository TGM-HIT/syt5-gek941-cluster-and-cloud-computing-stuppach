# SYT GK941 Cluster- und Cloud-Computing 
### "Container mit Kubernetes" 

**Authors:** Stuppig Markus 5DHIT, Wallpach Melissa 5BHIT
**Version:** 2024-11-14

## Einführung 
In dieser Aufgabe wird Kubernetes als aktuelle Lösung zum Starten und Verwalten von verteilten Rechnungsresourcen behandelt. Kubernetes bietet sich hier als eine beliebte, konstenlose Open-Source Lösung, die bei den meisten Cloud-Anbietern aber auch im eigenen Einsatz in einer On-Premise Cloud zum Einsatz kommt.

**Ziel** ist der Einsatz von Orchestrierungs-Engine zur Bereitstellung und Skalierung von Containeranwendungen.

## Fragestellungen 
### Unterschiede zwischen klassischen VMs und Containern

- **Ressourcennutzung**: VMs virtualisieren die gesamte Hardware und benötigen ein vollständiges Betriebssystem. Container teilen sich dagegen das Host-Betriebssystem und sind dadurch deutlich ressourcenschonender.

- **Isolierung**: VMs bieten eine stärkere Isolierung, da sie komplett voneinander getrennt sind. Container teilen sich den Kernel des Host-Systems, sind aber auf Prozessebene isoliert.

- **Startzeit**: Container starten in Sekunden, während VMs mehrere Minuten zum Booten benötigen können.

- **Portabilität**: Container sind hochportabel und können problemlos zwischen verschiedenen Umgebungen verschoben werden. VMs sind stärker an die zugrunde liegende Infrastruktur gebunden.

- **Skalierbarkeit**: Container lassen sich sehr schnell und effizient skalieren. Das Skalieren von VMs ist aufwendiger.

### Funktionen der Orchestrierung 

- **Automatisierte Bereitstellung** von Containern auf Basis von Konfigurationen

- **Skalierung** von Anwendungen durch Hinzufügen oder Entfernen von Container-Instanzen

- **Lastverteilung** zwischen Container-Instanzen

- **Service Discovery** und Routing zwischen Containern

- **Selbstheilung** durch automatischen Neustart fehlerhafter Container

- **Rollouts und Rollbacks** für kontrollierte Updates

- **Ressourcenmanagement** und Zuweisung von CPU, Speicher etc.

- **Konfigurationsmanagement** für Anwendungen

- **Persistenz** durch Verwaltung von Storage

### Zweck von Nodes in einem Kubernetes Cluster

- Sie stellen die **Ausführungsumgebung** für Container bereit

- Nodes sind die **Arbeitsmaschinen** des Clusters, auf denen die eigentlichen Workloads laufen

- Sie **hosten die Pods**, die die Container enthalten

- Nodes stellen **Rechenressourcen** (CPU, RAM) für die Ausführung von Containern zur Verfügung

- Sie führen den **Kubelet-Agenten** aus, der mit dem Control Plane kommuniziert

- Nodes ermöglichen die **Skalierung** des Clusters durch Hinzufügen weiterer Nodes

- Sie bieten **Netzwerk- und Storage-Ressourcen** für die Container[1][4]

Durch die Verteilung auf mehrere Nodes erreicht Kubernetes Hochverfügbarkeit und Lastverteilung für die Anwendungen im Cluster.
