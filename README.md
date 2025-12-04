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

# WP01
---
 
Beantwortung von 7 Fragen (WP1 - Betriebssystem Pre-Check).
 
Weitere beantwortung von 8 Fragen (WP 1 - Virtualisierung Exit-Check).
 
 
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

# Unterrericht 16.10.2025

- **Active Directory**

  - Verzeichnisdienst

  - 4 technische Komponenten:

    - LDAP (Lightweight Directory Access Protocol)
    - Kerberos (griechisch, für Authentifizierung)
    - SMB (Server Message Block)
    - DNS Domain Name System

  - Drei Bestandteile:

    - Schema (beschreibt alle möglichen Einträge(Schablone))
    - Konfiguration (beschreibt die Gesamtstruktur (Bäume))
    - Domain (beinhaltet Informationen zu sich selbst und allen Objekten)
  - Hierarchische Struktur

  - OU (Organisational Unit) als Gruppierungsmethode

  - Objekte:
    - Ressourcen
    - Konten:

      - Benutzer
      - Gruppe
      - Computer
      - Dienst

  - Alle Informationen befinden sich in einer Datenbank:

    - synchronisiert

  - Domain Controller (DC)

  - Gesamtstruktur (Forest): 
    - ![alt text](Unbenannt.png)
    - Directories 
    - Domänen
    - Standorte

# WP03 Active Dircrory

- Insterlation des Active Directory am syt-srv01
- Promotion des syt-srv01 zum Domain Controller

**Umsteigen auf Hyper VM**

- Da Virtual Box nicht funktioniert hat, steigen wir auf Hyper V um und erstellen einen neuen syt-srv01
- Alle erforderliche schritte wiederholen und hoffen, das es funktioniert

# Unterricht 23.10.2025

- Insterlation von syt-srv02, syt srv-pc01 wie auch syt-man01
- Insterlaionen beibehalten
- Änderungen: srv02 und man01 haben die gleichen Einstellungen, bei pc01 wurden ISO-Datei und TMP geändert
- Folgendes soll nach Konfiguration des man01 und srv02 stehen (bsp. man01):

![alt text](grafik-2.png)

- Zum testen klickt man auf den Namen, sucht nach syt.internal und folgendes sollte kommen:

![alt text](grafik-3.png)

(restart notwendig)

- Domäne bei allen drei auf syt.internal und namen jeweils ändern

- Folgende Konfigurationen bei man01:

![alt text](grafik-4.png)

- syt-srv01 bei man01 hinzufügen bzw. man01 managed srv01:

![alt text](grafik-5.png)

## **DHCP Optionen des syt-man1**

- Die DHCP Optionen bieten viele verschiedene Funktionen, finden tut man diese unter DHCP - DHCP Manager:

![alt text](grafik-6.png)

## **Active Directory Users and Computers**

- Gleich wie bei DHCP Option gibt es hier einige Informationen über die Users wie auch die Computers:

![alt text](grafik-7.png)

- Also Übung haben wir die Server man01 und srv02 von Computers in dem von uns erstellten OU Servers gedragt und gedroppt:

![alt text](grafik-8.png)

**Begrifflichkeiten:**

  - Identifikation -> Wer?
  - Authentifikation -> Eindeutiges Wer?
  - Autorisierung: -> Was darf er machen?

# Unterricht 6.11.2025

- Hinzufügen eines Alias Server im DNS-Manager unter syt-man01:
![alt text](grafik-10.png)

# WP03b Active Directory

- Erstellen von OUs (Departments) in Ressources und Peoples
![alt text](grafik-11.png)

- Erstellen der einzelnen Departments laut Vorgabe:
![alt text](grafik-12.png)

- Bei syt-pc01 mit dem bereits erstellten User (unter People) anmelden (System - About - Domain or workgroup):
![alt text](grafik-13.png)

- Unter User - Account kann man verschieden Sachen einstellen, wie z.B. den Account sprerren:
![alt text](grafik-14.png)

# Unterricht 13.11.2025

 ## **Powershell-Scripting**

 - interpretiert
 - TUI
 - .ps1
 - Textdateien
 - ISE (Sollte man nicht verwenden)
 - Inhalt:
      - Commandlets
      - Strukturen:
        - Verzweigungen
        - Schleifen
        - Funktionen
      - Kommentare

  ### **Aufgabenstellung:**
    
 #### WP 3c Powershell:
  - Script zur Usererzeugung
     - CSV
     - Excel
     - Anlegen von OUs (was passiert, wenn sie bereits existieren?)
     
# Unterricht 27.11.2025

  ## **File Server**

  - Über den man01-srv den Server srv02 managen bzw. folgender Befehl: "GetWindowsFeature -ComputerName syt-srv02", danach sollten viele Informationen über den Server "aufpoppen"

  - Folgende WindowsFeatures instalieren:
    - FS-Fileserver
    - FS-Data-Deduplication
    - FS-Resource-Manager

  - Instalieren folgender Features unter man01:
    - Unter syt-srv02: File Server Ressource Manager
    - Unter syt-man01: File Service Tools

  - File and Storage Services:
    - Features wie Volumes oder Disks

# Unterricht 04.12.2025

## **File-Sharing**

- Unter Properties eines (bspw.) Ordners kann man unter Sharing den Ornder teilen. Dabei gibt es auch advanced sharing, wo man die Rechte einstellen kann. Diese Rechte unterscheidet man nicht nur in Personen wie z.B. user oder group, sondern auch was diese Person ausführen kann.
- Zu den Rechten der Personen gehöhren:
  - read
  - write
  - execute
  - modify
  - list folder content
  - etc.

- Jede Freigabe die ein $ Zeichen im Pfad beim teilen hat, wird versteckt weitergegeben.

## Hinzufügen zweier Festplatten auf syt-syr01

- Die folgenden Festplatten wurden zum srv01 hinzugefüft: Data und Backup. 
- Auf dem man01 wurden dann beide Festplatten erstmal online gestellt, danach wurden sie inizialisiert und zuletzt wurden beiden eine jeweilige Volume hinzugefügt

## Verschiebung der Festplatten

- Die zwei Festplatten von srv01 auf srv02 verschieben. Dafür muss man sie einfach bei srv01 entfernen und bei srv02 hinzufügen (auf Durchsuchen klicken und dann die richtige Disk auswählen)

## Shares

- Unter dem Register Shares (Unter Disks und Volumes) kann man seine erstellten Ordner (in dem Fall backup) teilen an einen anderen Server (srv02):
![alt text](grafik-15.png) 