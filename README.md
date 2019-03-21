# LB 1 Yanik Vonderschmitt

  

## Inhaltsverzeichnis

  
[**Vorwort**](#Vorwort)

**Umgebung**
- [VirtualBox](#Virtualbox)
- [Git-Client](#Git-Client)
- [Vagrant](#Vagrant)
- [Sicherheit](#Sicherheit)
- [Netzwerk](#Netzwerk)

**Umsetzung**
- [Firewall](#Firewall)
- [Apache](#Apache)

**Schluss**
- [Reflexion](#Reflexion)
- [Wissensstand](#Wissensstand)
- [Lernschritte](#Lernschritte)

**Anhang**
- [Versionen](#Versionen)


  
  # Vorwort
  ## Markdown
  Die Dokumentation ist im Markdown Format geschrieben. Dieses Format eignet sich sehr für die Website GitHub, da dort der Inhalt sofort angezeigt wird. [Wikipedia](https://de.wikipedia.org/wiki/Markdown)
 ## GitHub
 GitHub ist eine Website um eigene Software-Entwicklungsprojekte online zu stellen. Dabei stellt GitHub den Speicherplatz zur Verfügung. GitHub arbeitet mit "repositories" was nichts anderes wie Speicherorte sind. Mittels Git-Client können ganze Repositories lokal auf den Computer importiert werden (Pull) und wiederum aufs auf Git-Hub exportiert werden(Push). So kann lokal gearbeitet werden. Hier die [Website](https://github.com/)

# Umgebung

## VirtualBox
### Infos

![VirtualBox](images/virtualbox.PNG)

Als Virtualisierungsplattform wird VirtualBox benutzt. Installiert wird dies simpel über ihre Website. [Link](https://www.virtualbox.org/wiki/Downloads). Schlussendlich werden die von Vagrant erstellten VMs in VirtualBox bereitgestellt. Alternativ könnten in VirtualBox VMs mit .iso Dateien per Hand installiert werden.

## Git-Client
### Infos
![VirtualBox](images/gitclient.PNG)

Git Client wird benutzt um Repositories und Vagrant zu bedienen. Befehle werden dazu in die Git Client Kommandozeile geschrieben. Ihn kann man auf dieser [Website](https://git-scm.com/downloads) herunterladen und installieren.
### Git-Client Befehle
Mittels Git-Befehle können Repositories verwaltet werden.

**GitHub Account hinterlegen**
Um mit seinen Online Repositories zu arbeiten muss der GitHub Account hinterlegt werden.
 ```Shell
      $ git config --global user.name "<username>"
	  $ git config --global user.email "<e-mail>"
 ```
**Repositories importieren**
So werden Online Repositories lokal importiert.
```Shell
	$ cd Wohin\auch\immer
	$ git clone git@github.com:<Ihr Name>/my_M300.git
 ```
**Repositories runterladen**
Falls es Änderungen im Online Repository gibt, kann dieser so importiert werden. Dabei wird das veraltete auf die neue Version angepasst.
 ```Shell
	$ git pull
 ```
 
**Repositories hochladen**
Um das lokale Repository online hochzuladen wird dieser Befehl benutzt. Dabei wird dann die Online Version mit der lokalen überschrieben.
 ```Shell
      $ git commit -m "Mein Kommentar"
      $ git push
 ```
  

## Vagrant
### Infos

![VirtualBox](images/Vagrant.PNG)

Mit Vagrant ist es möglich ganz einfach VMs zu erstellen. Die Grundlage dabei ist eine Base-Box eines OS. Dies ist nichts anderes als eine blanke VM des OS. Mit einem Vagranfile wird dann diese Base-Box ausgewählt und Konfiguriert. So kann ganz einfach VMs erstellt werden.

### Vagrant Befehle
Vagrant wird per Git-Client mit Befehlen gesteuert.
**Neues Vagrantfile erstellen**
Zuerst muss in den gewählten Ordner gewechselt werden und dort wird dann das Vagrantfile erstellt
```Shell
      $ cd Wohin\auch\immer
      $ vagrant init
 ```
**VM erstellen lassen**
Um eine VM zu erstellen muss zuerst ins gleiche Verzeichnis wie das Vagrantfile gewechselt werden und dann wird die VM erstellt.
 ```Shell
      $ cd Zum\Vagrantfile
      $ vagrant up
 ```

**Mittels SSH auf VM verbinden**
Es ist möglich per SSH Verschlüsselung sich mit der VM zu verbinden. Dazu muss ins gleiche Verzeichnis wie die VM gewechselt und dann verbunden werden.

```Shell
      $ cd Zur\VM
      $ vagrant ssh
 ```
**VM herunterfahren**
Wenn man die VM herunter fahren möchte muss dieser Befehl eingegeben werden.
```Shell
      $ Vagrant halt
 ```
  
 **VM löschen**
Wenn die VM gelöscht werden will wird dieser Befehl benutzt. Dazu muss sie herunter gefahren sein.
```Shell
      $ Vagrant destroy
 ```
 ### Vagrant Cloud-boxen
 Grosser Vorteil von Vagrant ist die Auswahl von den Base-boxen, aus welchen dann die VMs gemacht werden. Die Auswahl ist online auf dieser [Website](https://app.vagrantup.com/boxes/search) zu finden.
 

## Visual Code Studio

![VirtualBox](images/vcs.PNG)

Visual Code Studio ist ein Quelltext Editor von Microsoft. Damit können Programme in verschiedenen Programmiersprachen geschrieben werden. Plug-Ins können installiert werden und das arbeiten somit erleichtern.

### Plug-Ins

# Sicherheit

## SSH Key zu GitHub

  ![VirtualBox](images/ssh.PNG)

Mit SSH können Verbindungen verschlüsselt werden. Dies wird hier eingesetzt, um die Verbindung zum Online Repository zu sichern.

## SSH Tunnel
Es ist möglich per SSH Verschlüsselung sich mit der VM zu verbinden. Dazu muss ins gleiche Verzeichnis wie die VM gewechselt und dann verbunden werden.
```Shell
      $ cd Zur\VM
      $ vagrant ssh
 ```

## Firewallrules

## Benutzer

## Reverse Proxy

# Netzwerk

## Firewall
### Installation

### Test

## Apache
### Installation

### Test

# Schluss
## Reflexion

## Wissensstand Vorher-Nachher

## Lernschritte

# Anhang
## Versionen

