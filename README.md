# kali-anonstealth

ParrotSec's anonsurf und stealth, portiert für die Arbeit mit Kali Linux.

## Wie man diese Repo benutzt

Dieses Repo enthält die Quellen der beiden Pakete anonsurf und pandora von ParrotSec kombiniert in einem.

Es wurden Änderungen vorgenommen, um die DNS-Server von Private Internet Access (anstelle von FrozenDNS) zu verwenden, sowie Korrekturen für Benutzer, die die Anwendung resolvconf nicht verwenden. Ich habe einige Funktionen wie die GUI und iceweasel in ram entfernt.

Dieses Repo kann in ein deb-Paket kompiliert werden, um es korrekt auf einem Kali-System zu installieren.

Der einfachste Weg, diese zum Laufen zu bringen, ist, einfach den Installer auszuführen. Weitere Informationen finden Sie im Abschnitt über die Installation.

HINWEIS: Dies kann mit jedem Debian-/Ubuntu-System funktionieren, aber sie wurde nur auf einem Kali-Rolling-Amd64-System getestet

## Usage
### Pandora
Pandora überschreibt das RAM automatisch, wenn das System heruntergefahren wird. Pandora kann auch manuell ausgeführt werden:
```bash
pandora bomb
```

HINWEIS: Dadurch wird der gesamte System-Cache gelöscht, einschließlich aktiver SSH-Tunnel oder -Sitzungen.

### anonsurf
Anonsurf wird das gesamte System unter TOR mit IPTables anonymisieren. Es wird Ihnen auch erlauben, i2p zu starten und zu stoppen.

HINWEIS: Führen Sie dies NICHT als ```service anonsurf $COMMAND``` aus. Führen Sie dies als ```anonsurf $COMMAND`` aus.

```bash
Benutzung:
 anonsurf {start|stop|restart|change|status}

 start - Starten Sie das systemweite anonyme
           Tunneling unter TOR-Proxy durch iptables
 stop - Ursprüngliche iptables-Einstellungen zurücksetzen
          und zurück zur freien Navigation
 restart - Kombiniert "Stopp" und "Start" Optionen
 change - Änderungen der Identität Neustart von TOR 
 status - Prüfen Sie, ob AnonSurf richtig funktioniert
----[ I2P zugehörige Funktionen ]----
 starti2p - Starte i2p Dienste
 stopi2p - Stoppe i2p Dienste
```

## Installation
Dieses Paket wird mit einem Installationsprogramm geliefert, das die Dinge extrem einfach macht:

```bash
./installer.sh
```

Sobald das Installationsprogramm abgeschlossen ist, können Sie sowohl das anonsurf- als auch das pandora-Modul verwenden.
