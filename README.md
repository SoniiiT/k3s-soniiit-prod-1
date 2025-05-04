# K3s-SoniiiT-Prod-1

## Über Kubernetes und K3s

Kubernetes ist ein Open-Source-Container-Orchestrierungssystem, das die Automatisierung der Bereitstellung, Skalierung und Verwaltung von containerisierten Anwendungen ermöglicht. K3s ist eine leichtgewichtige, vollständig konforme Kubernetes-Distribution, die speziell für Edge-Computing, IoT und ressourcenbeschränkte Umgebungen entwickelt wurde.

## Repository-Inhalt

Dieses Repository enthält die tatsächlichen Konfigurationen und Manifests für mein K3s-Produktionscluster. Hier finden Sie:

- Kubernetes-Manifests für verschiedene Anwendungen und Services
- Konfigurationsdateien für Cluster-Komponenten
- Deployment-Skripte und Automatisierungstools
- Dokumentation zur Cluster-Architektur und -Konfiguration

## Verwendung

Die Konfigurationen in diesem Repository sind speziell auf mein Produktionscluster zugeschnitten. Sie können als Referenz für ähnliche Setups dienen, sollten aber entsprechend Ihrer spezifischen Anforderungen angepasst werden.

## Renovate für Kubernetes

Dieses Repository nutzt [Renovate](https://github.com/renovatebot/renovate) zur automatischen Aktualisierung von Abhängigkeiten. Renovate unterstützt:

- Kubernetes-Manifeste (YAML-Dateien)
- Helm-Charts und deren Versionen
- Container-Images in Kubernetes-Deployments

### Konfiguration

Um Renovate für Kubernetes-Dateien zu aktivieren, fügen Sie folgende Konfiguration in Ihre `renovate.json` ein:

```json
{
  "kubernetes": {
    "fileMatch": ["\\.yaml$", "\\.yml$"],
    "enabled": true
  },
  "helm": {
    "fileMatch": ["Chart\\.yaml$"],
    "enabled": true
  }
}
```

### Unterstützte Aktualisierungen

Renovate kann:
- Container-Image-Versionen in Deployments aktualisieren
- Helm-Chart-Versionen überprüfen und aktualisieren
- Kubernetes-API-Versionen überwachen
- Abhängigkeiten in Helm-Charts aktualisieren

### Best Practices

- Stellen Sie sicher, dass Ihre Kubernetes-Dateien korrekt formatiert sind
- Verwenden Sie explizite Versionen für Container-Images
- Definieren Sie klare Update-Strategien in der Renovate-Konfiguration