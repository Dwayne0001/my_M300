# LB 1 Yanik Vonderschmitt

  

## Inhaltsverzeichnis

  
**Vorwort**

**Umgebung**
	- Virtualbox
	-  Vagrant
	- Git-Client
	- Sicherheit

**Umsetzung**
- Uncomplicated Firewall (UFW)
- Apache Webserver

**Schluss**
- Reflexion
- Wissensstand
- Lernschritte

**Anhang**


  
  

# Umgebung

## VirtualBox
### Infos

![VirtualBox](images/virtualbox.PNG)

Als Virtualisierungsplattform wird VirtualBox benutzt. Installiert wird dies simpel über ihre Website. [Link](https://www.virtualbox.org/wiki/Downloads). Schlussendlich werden die von Vagrant erstellten VMs in VirtualBox bereitgestellt. Alternativ könnten in VirtualBox VMs mit .iso Dateien per Hand installiert werden.

  

## Vagrant
### Infos

![VirtualBox](images/Vagrant.PNG)

Mit Vagrant ist es möglich ganz einfach VMs zu erstellen. Die Grundlage dabei ist eine Base-Box eines OS. Dies ist nichts anderes als eine blanke VM des OS. Mit einem Vagranfile wird dann diese Base-Box ausgewählt und Konfiguriert. So kann ganz einfach VMs erstellt werden.

### Vagrant Befehle
Vagrant wird per Git-Client mit Befehlen gesteuert. Zum Git-Client wird weiter unten eingegangen. 
 ```Shell
      Generating public/private rsa key pair.
 ```

  

## Visal Code Studio

![VirtualBox](images/vcs.PNG)

Visual Code Studio ist ein Quelltext Editor von Microsoft. Damit können Programme in verschiedenen Programmiersprachen geschrieben werden. Plug-Ins können installiert werden und das arbeiten somit erleichtern.

  

## Git Client

![VirtualBox](images/gitclient.PNG)

Git Client wird benutzt um Repositories und Vagrant zu bedienen. Befehle werden dazu in die Git Client Commandzeile geschrieben.

  

## SSH Keys

![VirtualBox](images/ssh.PNG)

Mit SSH können Verbindungen verschlüsselt werden. Dies wird hier eingesetzt, um die Verbindung zum Online Repository zu sichern.

  

# Lernumbgebung

  

# Vagrant

  

# Sicherheit

  

# PIHole