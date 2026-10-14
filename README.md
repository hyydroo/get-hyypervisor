# get-hyypervisor

Installationsskript für **hyypervisor** (Gameserver-Portal) und seine Bauteile `hyyper-node` und `hyyper-forwarder`.
Dieses Repo enthält nur das Skript; es wird aus dem Hauptprojekt übernommen.

## Installieren (Debian 12/13, Ubuntu 22.04+, als root)

```bash
bash <(curl -fsSL get.hyypervised.de)
```

Mit `sudo` (funktioniert auch, wenn `sudo` keine offenen Dateideskriptoren durchreicht):

```bash
curl -fsSL get.hyypervised.de | sudo bash
```

(`get.hyypervised.de` leitet auf `https://raw.githubusercontent.com/hyydroo/get-hyypervisor/main/get-hyypervisor` weiter; diese Adresse funktioniert auch direkt.)

Das Skript fragt, was auf dieser VM installiert werden soll: nur Portal, nur Node, nur Forwarder oder eine Kombination.
Danach verwaltest du alles mit `get-hyypervisor` (`update`, `status`, `uninstall`, …).

Direkt ohne Menü, zum Beispiel:

```bash
curl -fsSL get.hyypervised.de | sudo bash -s -- install portal
```

## Vor dem Ausführen prüfen

Das Skript läuft als root. Lies es vorher, es ist eine einzelne Textdatei: [get-hyypervisor](get-hyypervisor).
Es richtet systemd-Dienste ein, legt Benutzer an und lädt das Programm aus dem Container-Image
`ghcr.io/hyydroo/hyypervisor` (Prüfung gegen Fehlbedienung: nur HTTPS oder private Netze, Skriptprüfung vor dem Ablegen).
Ist das Image nicht öffentlich, fragt das Skript einmal nach einem GitHub-Zugang mit Leserecht auf Pakete
(`read:packages`) und meldet sich danach wieder ab.

---

Installer for **hyypervisor** (game server portal) and its components `hyyper-node` and `hyyper-forwarder`.
Run the command above as root on Debian 12/13 or Ubuntu 22.04+. Read the script first; it is a single text file.
