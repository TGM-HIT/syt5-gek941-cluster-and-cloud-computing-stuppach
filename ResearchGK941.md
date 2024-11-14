# GK941 - Research 

## Fragestellungen zu Kubernetes

## Definition
Kubernetes is an open source container orchestration engine for automating deployment, scaling, and management of containerized applications. The open source project is hosted by the Cloud Native Computing Foundation (CNCF).

### VMs vs Container

- **Ressourcennutzung**: VMs virtualisieren die gesamte Hardware und benötigen ein vollständiges Betriebssystem. Container teilen sich dagegen das Host-Betriebssystem und sind dadurch deutlich ressourcenschonender.

- **Isolierung**: VMs bieten eine stärkere Isolierung, da sie komplett voneinander getrennt sind. Container teilen sich den Kernel des Host-Systems, sind aber auf Prozessebene isoliert.

- **Startzeit**: Container starten in Sekunden, während VMs mehrere Minuten zum Booten benötigen können.

- **Portabilität**: Container sind hochportabel und können problemlos zwischen verschiedenen Umgebungen verschoben werden. VMs sind stärker an die zugrunde liegende Infrastruktur gebunden.

- **Skalierbarkeit**: Container lassen sich sehr schnell und effizient skalieren. Das Skalieren von VMs ist aufwendiger.

### Vorteile von Kubernetes im Detail
Container sind ähnlich wie virtuelle Maschinen (VMs), besitzen jedoch eine weniger strikte Isolation, um das Betriebssystem (OS) zwischen den Anwendungen gemeinsam zu nutzen. Daher gelten Container als leichtgewichtig. Ähnlich wie eine VM verfügt ein Container über sein eigenes Dateisystem, eine Zuweisung von CPU, Speicher, Prozessraum und mehr. Da sie von der zugrunde liegenden Infrastruktur entkoppelt sind, sind Container portabel über verschiedene Clouds und Betriebssysteme hinweg.

Container haben an Beliebtheit gewonnen, da sie zusätzliche Vorteile bieten, wie:

* **Agile Anwendungserstellung und -bereitstellung:** Die Erstellung von Container-Images ist einfacher und effizienter im Vergleich zur Nutzung von VM-Images.
* **Kontinuierliche Entwicklung, Integration und Bereitstellung:** Sie ermöglichen zuverlässige und häufige Erstellung und Bereitstellung von Container-Images mit schnellen und effizienten Rollbacks (dank der Unveränderlichkeit der Images).
* **Trennung der Verantwortlichkeiten von Entwicklung und Betrieb:** Anwendungs-Container-Images werden zur Build-/Release-Zeit erstellt und nicht erst zur Bereitstellungszeit, wodurch Anwendungen von der Infrastruktur entkoppelt werden.
* **Observierbarkeit:** Bietet nicht nur OS-Informationen und Metriken, sondern auch Anwendungsstatus und andere Signale.
* **Umgebungskonsistenz über Entwicklung, Test und Produktion hinweg:** Läuft auf einem Laptop genauso wie in der Cloud.
* **Portabilität über Cloud- und OS-Distributionen hinweg:** Funktioniert auf Ubuntu, RHEL, CoreOS, vor Ort, auf großen öffentlichen Clouds und überall sonst.
* **Anwendungszentriertes Management:** Hebt das Abstraktionsniveau von der Ausführung eines OS auf virtueller Hardware zur Ausführung einer Anwendung auf einem OS mit logischen Ressourcen.
* **Locker gekoppelte, verteilte, elastische, unabhängige Microservices:** Anwendungen werden in kleinere, unabhängige Teile zerlegt, die dynamisch bereitgestellt und verwaltet werden können – keine monolithische Struktur auf einer großen Maschine mit einem einzigen Zweck.
* **Ressourcenisolation:** Berechenbare Anwendungsleistung.
* **Ressourcennutzung:** Hohe Effizienz und Dichte.


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

### Funktionen von Kubernetes im Detail 

* **Service discovery and load balancing** Kubernetes kann Container über DNS-Namen oder IP-Adressen zugänglich machen und den Netzwerkverkehr bei hohem Traffic automatisch verteilen.
* **Storage orchestration** ermöglicht das automatische Einbinden eines gewünschten Speichersystems, z.B. lokale oder Cloud-Speicher.
* **Automated rollouts and rollbacks** Definiere den gewünschten Zustand der Container, und Kubernetes aktualisiert sie automatisch, indem es neue Container erstellt oder alte entfernt.
* **Automatic bin packing** Kubernetes platziert Container optimal auf Knoten im Cluster, um Ressourcen effizient zu nutzen.
* **Self-healing** Kubernetes startet fehlerhafte Container neu, ersetzt nicht funktionierende und entfernt sie aus dem Dienst, bis sie wieder einsatzbereit sind.
* **Secret and configuration management** Sensible Daten wie Passwörter und Token lassen sich sicher speichern und aktualisieren, ohne Container neu zu bauen.
* **Batch execution** Kubernetes verwaltet auch Batch- und CI-Workloads und ersetzt fehlerhafte Container.
* **Horizontal scaling** Skalierung der Anwendung per Befehl, UI oder automatisch basierend auf CPU-Auslastung.
* **IPv4/IPv6 dual-stack** Zuweisung von IPv4- und IPv6-Adressen an Pods und Services.
* **Designed for extensibility** Funktionen lassen sich hinzufügen, ohne den Kubernetes-Quellcode anzupassen.

### Zweck von Nodes in einem Kubernetes Cluster

- Sie stellen die **Ausführungsumgebung** für Container bereit

- Nodes sind die **Arbeitsmaschinen** des Clusters, auf denen die eigentlichen Workloads laufen

- Sie **hosten die Pods**, die die Container enthalten

- Nodes stellen **Rechenressourcen** (CPU, RAM) für die Ausführung von Containern zur Verfügung

- Sie führen den **Kubelet-Agenten** aus, der mit dem Control Plane kommuniziert

- Nodes ermöglichen die **Skalierung** des Clusters durch Hinzufügen weiterer Nodes

- Sie bieten **Netzwerk- und Storage-Ressourcen** für die Container[1][4]

Durch die Verteilung auf mehrere Nodes erreicht Kubernetes Hochverfügbarkeit und Lastverteilung für die Anwendungen im Cluster.

