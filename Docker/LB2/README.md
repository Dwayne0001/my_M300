# **LB2** **Docker**  <!-- omit in toc -->

## Inhalt <!-- omit in toc -->
- [Kapitel 1 Der Service](#kapitel-1-der-service)
- [Kapitel 2 Technische Angaben](#kapitel-2-technische-angaben)
  - [Netzwerkplan](#netzwerkplan)
  - [Code](#code)
  - [Anleitung für den Betrieb](#anleitung-f%C3%BCr-den-betrieb)
- [Kapitel 3 Testing](#kapitel-3-testing)
- [Kapitel 4 Troubleshooting](#kapitel-4-troubleshooting)
- [Quellen](#quellen)

# Kapitel 1 Der Service

Als Service wird eine eigene **MySQL** **Datenbank** mit **PHPMyAdmin** administriert. Anstatt per Command Line wird bei PHPMyAdmin die MySQL Datenbank per Webinterface bedient. Durch den Visuellen Faktor und dem übersichtlichem GUI wird die Arbeit mit den MYSQL Datenbank sehr vereinfacht.

Per Interner Verlinkung zwischen MySQL und PHPMyAdmin kann dies ermöglicht werden.

![GUI](Images/GUI.PNG)

# Kapitel 2 Technische Angaben

Der Service wird mit 2 Docker Container realisiert. Bei ersten wird MySQL und beim zweiten PHPMyAdmin installiert. Durch das custom "Net1" Netzwerk können die Container kommunizieren.

| **Info**       | **Container** 1 |   **Container** 2 |
| :------------- | :-------------: | ----------------: |
| Container Name |      MySQL      |        PHPMyAdmin |
| Docker Image   |    mysql:5.7    | phpmyadmin:latest |
| Netzwerk       |      Net1       |              Net1 |
| IP             |      DHCP       |              DHCP |

## Netzwerkplan

![Netzwerk](Images/netzwerk.png)

Die Container werden innerhalb von der Docker VM aufgesetzt. Das Net1 wird auf den Modus "Bridge" konfiguriert, sodass die Container vom Host erreichbar sind. Dabei ist der Host auch der Gateway zum Internet.

Die beiden Container werden am Net1 angehängt und bekommen per DHCP eine IP im Range 127.0.0.x/24. Der Gateway erhält immer die IP 172.0.0.1.

Mit einem Link kann der PHPMyAdmin auf den MySQL Container mit den Datenbanken zugreifen. Wie dies Funktioniert, wird im Abschnitt **Code** eingegangen.

Damit der Host auf das Webinterface des PHPMyAdmin zugreifen kann, muss der Container Port 80 auf den Host Port 8080 gemapt werden. Wie dies Funktioniert, wird im Abschnitt **Code** eingegangen.

## Code
Das Projekt wurde mit einem Docker Compose File realisiert. In diesem File werden alle Container und Netzwerk Parameter definiert. Mit diesem Behefl wird dann die Struktur aufgesetzt:
```Shell
docker-compose -f ʺPfad\zum\File\docker-compose.ymlʺ up -d --build
 ```
"-d" definiert, dass die Container im Hintergrund aufgesetzt wird.

"-f" setzt den den Pfad zum docker-compose.yml File

Hier der Code des docker-compose.yml File:
```Shell
version: '3.7'                          # Version von docker-compose.yml
services:                               # Auflistung der Services
  db:                                   # Anfang MySQL Service
    image: mysql:5.7                    # Docker Image
    container_name: mysql               # Containername
    networks:                           # Anfang Netzwerkkonfiguration
    - Net1                              # Net1 als Netzwerk gesetzt
    restart: always                     # Nach erstellen Neustarten
    environment:                        # Anfang environment Parameter
      MYSQL_ROOT_PASSWORD: 'Qawsed123'  # Rootpasswort von MySQL setzen
      MYSQL_DATABASE: New_Database      # Neue Datenbank erstellt

  php:                                  # Anfang PHPMyAdmin Service
    depends_on:                         # Anfang Abhänigkeit
      - db                              #Abhängig von Service db
    image: phpmyadmin:latest            # Docker Image
    container_name: PHPMyAdmin          # Containername
    networks:                           # Anfang Netzwerkkonfiguration
    - Net1                              # Net1 als Netzwerk gesetzt
    ports:                              # Anfang Portmapping
      - "8080:80"                       # Container Port 80 auf Localhost Port 8080
    restart: always                     # Nach erstellen Neustarten
    environment:                        # Anfang environment Parameter
      PMA_HOST: db                      # MySQL Datenbank ist db

networks:                        # Anfang allgemeine Netzwerkkonfiguration
  Net1:                                 # Netzwerk Net1 erstellt
 ```

## Anleitung für den Betrieb

# Kapitel 3 Testing

# Kapitel 4 Troubleshooting

# Quellen

**Benutzte** **Images**:

PHPMyAdmin:latest [Docker Hub][php]

MySQL:5.7 [Docker Hub][sql]

**Benutzte** **Websites**:

Mein GitHub [Repository][mygit]

Modul 300 [Repository][m300git]

Docker Compose [Dokumentation][dc]

<!-- Link Index -->

[sql]: https://hub.docker.com/_/mysql

[php]: https://hub.docker.com/r/phpmyadmin/phpmyadmin/

[mygit]: https://github.com/YanikVonderschmitt/my_M300

[m300git]: https://github.com/mc-b/M300

[dc]: https://docs.docker.com/compose/