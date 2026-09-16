# HiveBus Releases

Dieses Repository enthält die öffentlichen Debian-Release-Pakete und den Installer für HiveBus.

HiveBus prüft Modbus-TCP- und Modbus-RTU-Geräte, liest Geräteinformationen sowie Register und ermöglicht kontrollierte Schreibzugriffe. Modbus RTU verwendet auf dem eHive One den Hardware-RS485-Port `/dev/ttyS2`.

## Installation und Update

```bash
curl -fsSL https://raw.githubusercontent.com/ehive-dev/HiveBus_releases/main/install.sh | sudo bash
```

Eine bestimmte Version installieren:

```bash
curl -fsSL https://raw.githubusercontent.com/ehive-dev/HiveBus_releases/main/install.sh | sudo bash -s -- --tag v0.3.0
```

## Service

```bash
systemctl status hivebus --no-pager
journalctl -u hivebus -f
```

HiveBus ist anschließend standardmäßig unter `http://<ehive-ip>:8091` erreichbar. Der lokale Health-Check lautet:

```bash
curl http://127.0.0.1:8091/healthz
```

## Sicherheit

Schreibzugriffe auf Modbus-Register können den Anlagenbetrieb verändern. Verwende ausschließlich dokumentierte Register, Werte und Datentypen des Geräteherstellers.

## Lizenz

HiveBus wird unter der MIT-Lizenz veröffentlicht. Siehe `LICENSE`.
