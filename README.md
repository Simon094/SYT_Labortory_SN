# Virtualisierung

## Begriffsdefinition

- **Host**: Das physische System, auf dem Virtualisierung läuft.
- **Guest**: Das virtuelle System, das innerhalb des Hosts betrieben wird.

---

## Virtualisierungsarten

### Virtuelle Maschine (VM)

- Guest: Läuft als unabhängiges System innerhalb der VM.
- Bildet vollständige Rechenarchitektur eines Computers nach.

### Hypervisor

- Abstraktionsschicht zwischen Hardware und virtuellen Maschinen.
- Erlaubt Betrieb mehrerer VMs gleichzeitig:
  - Unterschiedliche Betriebssysteme und Architekturen möglich.
- Nutzt Virtualisierungsfunktionen der CPU.

#### Problempunkte

- Effizienzverlust durch Abstraktionsschicht.
- Gegenseitige Beeinflussung der VMs durch gemeinsame Ressourcennutzung.

#### Hypervisor Typ 1

- Läuft direkt auf der Hardware (Bare Metal).
- Sehr ressourceneffizient.

#### Hypervisor Typ 2

- Läuft als Anwendung auf einem Host-Betriebssystem.
- Weniger effizient, aber einfacher zu implementieren.

---

### Containervirtualisierung

- Komplette Laufzeitumgebung in isolierten Containern.
- Es wird **kein zusätzliches Betriebssystem** gestartet.
  - Ressourcenschonend.
  - Alle Container nutzen den **Kernel des Hosts**.

#### Problempunkte

- Isolation der Container ist technisch komplex.
- Sicherheitslücken im Host-Kernel betreffen alle Container.
- Systembibliotheken müssen regelmäßig aktualisiert werden.

---

### Anwendungsvirtualisierung

- Anwendungen laufen in einer **isolierten Umgebung** (Sandbox).
- Virtualisierung anderer Betriebssysteme möglich.
- Gute **Portierbarkeit** der Anwendung.
- Ressourcenschonender als vollständige VMs.

#### Problempunkte

- Nicht alle Anwendungen sind virtualisierbar.
- **Lizenzierungsprobleme** können auftreten.

---

### Netzwerkvirtualisierung

- Abbildung und Virtualisierung von Netzwerkkomponenten:
  - Switches, Router, Firewalls usw.

*Stunde 2**
---
 
Beantwortung von 7 Fragen (WP1 - Betriebssystem Pre-Check). Insgesamt 7/7 richtig.
 
Weitere beantwortung von 8 Fragen (WP 1 - Virtualisierung Exit-Check). Insgesamt 6/8 richtig.
 
 
### Aufgabenstellung 25.09.2025
---
WP 1 - Teilaufgabenstellung 1
VM: syt-man01
 
Sehen Sie sich im GUI von Windows Server 2025 um. In wie fern unterscheidet sich dieses von der Desktopversion von Windows?
 
Welche Unterschiede fallen Ihnen bei den Dienstprogrammen auf?
 
Beantworten Sie diese Fragestellungen in Ihrer Markdown Dokumentation.
 
 
# Bearbeitung der Teilaufgabenstellung 1
---
 
**VM:** `syt-man01`  
**Thema:** Unterschiede Windows Server 2025 vs. Desktopversion (z. B. Windows 11)
 
## Hauptunterschiede in der GUI
- Kein Microsoft Store, keine Consumer-Apps (z. B. Xbox, Wetter).
- Startmenü ist schlicht, keine Werbung oder „Empfohlen“-Sektion.
- Server Manager öffnet sich automatisch beim Start.
- Oberfläche wirkt technischer, weniger auf Benutzerfreundlichkeit optimiert.
 
## Unterschiede in den Dienstprogrammen
- **Nur im Server:**  
  - Server Manager  
  - Rollen- & Featureverwaltung  
  - Active Directory, DNS, DHCP  
  - Hyper-V Manager  
- **Nicht vorhanden:**  
  - Cortana, Widgets  
  - Multimedia-Apps  
  - Microsoft Store
 
## Fazit
Windows Server 2025 ist auf Verwaltung und Stabilität optimiert – ohne unnötige Apps, dafür mit vielen Admin-Tools, die in der Desktopversion fehlen.

# WP02 DHCP

- **Aufgabenstellung 1:** Konfiguration eines DHCP im Server syt-srv01
  - 15 eingeben um PowerShell zu aktivieren
  - Instalation des DHCP-Servers
  - Konfiguration des Default Gateway
  - Erstellung/Konfiguration des DNS-Servers
  - Am Ende zur Überprüfung das alles funktioniert hat, gibt man bei server "syt-man01" ipconfig /renew ein und danach sollte es die richtige IPv4-Adresse anzeigen:![alt text](grafik.png)

- **Aufgabenstellung 2:** Konfiguration eines Managament Servers
  - In Server man01 unter dem Register Manage die DHCP-Tools hinzufügen
  - Danach auf Add Server, unter DNS den Server syt-02 suchen
  - Server hinzufügen, danach unter All Servers sollte es so aussehen:
  ![alt text](grafik-1.png)
