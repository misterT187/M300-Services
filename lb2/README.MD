# M300 LB2
Plattforübergreifende Dienste in ein Netzwerk integrieren

## Autor
Thomas Mägerle

## Inhaltsverzeichnis

- [Einführung](#einfuehrung) 
    - [Git Einrichten](#giteinrichten)
    - [Markdown](#markdown)
    - [Vagrant](#vagrant)
    - [Befehle](#Befehle)
    - [Nginx](#nginx)
    - [UFW](#ufw)
- [Code](#code)
- [Anleitung](#anleitung)
- [Testen](#testen)
- [Netzwerkplan](#netzwerkplan)
- [Quellenverzeichnis](#quellenverzeichnis)

<a name="einfuehrung"></a>
## Einführung
Als erstes werde ich eine kleine Einführung über alle wichtigen Services.

<a name="giteinrichten"></a>
### Git Einrichten
```
git config --global user.name "username"
git config --global user.email "E-Mail"
```

<a name="markdown"></a>
## Markdown
Markdown bearbeiten in Code:
https://code.visualstudio.com/docs/languages/markdown

Markdown wird zum darstellen einer Datei gebraucht in einem "Humanen Stil".
<br>

\# H1 Übertitel 1 <br>
\## H2 Übertitel 2 <br>
\### H3 Übertitel 3 <br>
\#### H4 Übertitel 4 <br>
\##### H5 Übertitel 5 <br>
\###### H6 Übertitel 6 <br>
<br>
\Alternatively, for H1 and H2, an underline-ish style: <br>

<p> \Alt-H1 <br>
\====== </p>
<br>
<p> \Alt-H2 <br>
\------ </p>
<br>

<a name="vagrant"></a>
## Vagrant
Vagrant ist eine freie Ruby-Anwendung zum Erstellen und Verwalten virtueller Maschinen.[2] Vagrant ermöglicht einfache Softwareverteilung (englisch Deployment) insbesondere in der Software- und Webentwicklung und dient als Wrapper zwischen Virtualisierungssoftware wie VirtualBox, KVM/QEMU, VMware und Hyper-V und Software-Configuration-Management-Anwendungen beziehungsweise Systemkonfigurationswerkzeugen wie Chef, Saltstack und Puppet.

<a name="befehle"></a>

### Befehle
| Befehl            | Funktion                                             |
| -------------     | ---------------------------------------------------- | 
| ```vagrant init```      | Initialisiert im aktuellen Verzeichnis eine Vagrant-Umgebung und erstellt, falls nicht vorhanden, ein Vagrantfile. |
| ```vagrant up```        | Erzeugt und Konfiguriert eine neue Virtuelle Maschine, basierend auf dem Vagrantfile. |
| ```vagrant ssh```       | Baut eine SSH-Verbindung zur gewünschten VM auf. |
| ```vagrant status```    | Zeigt den aktuellen Status der VM an. |
| ```vagrant port```      | Zeigt die Weitergeleiteten Ports der VM an. |
| ```vagrant halt```      | Stoppt die laufende Virtuelle Maschine. |
| ```vagrant destroy```   | Stoppt die Virtuelle Maschine und zerstört sie. |

<a name="nginx"></a>
### Nginx
Nginx ist eine Webserver-Software welche zusätzlich auch noch Reverse Proxy und E-Mail-Proxy unterstützt.

<a name="ufw"></a>
### UFW
UFW steht für Uncomplicated Firewall. Sprich es ist einfach eine sehr einfach zu handhabende Firewall.

<a name="code"></a>
## Code
Hier sieht man den verwendeten Code und die erklärung zu dem jeweiligen Command.

Vagrant konfiguration einleiten

    `Vagrant.configure(2) do |config|`


Welche Ubuntu Version verwendet wird
    
    `config.vm.box = "ubuntu/bionic64"`


Port forwarding von 80 auf 100.
    
    `config.vm.network "forwarded_port", guest:80, host:100, auto_correct: false`


Bestimmen mit welchem Programm die VM erstellt werden soll
    
    `config.vm.provider "virtualbox" do |vb|`


Festlegen wieviel Arbeitsspeicher verwendet werden darf
    
    `vb.memory = "1024"`

Ende der Vagrant Config
    
    `end`


VM Config einleiten. Festlegen das folgende zeilen in der Shell geschrieben werden.

    `config.vm.provision "shell", inline: <<-SHELL`


Neueste Updates herunterladen

    `sudo apt-get update`


Installieren von diversen Diensten
    
    `sudo apt-get install -y \`
    `ca-certificates \`
    `curl \`
    `gnupg \`
    `ufw \`
    `lsb-release`


Verifikation des Dockerimages

    `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor `-o /usr/share/keyrings/docker-archive-keyring.gpg`
    `echo \`
    `"deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/`docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \`
    `$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > ``/dev/null`


Firewall Rules setzten
    
    `sudo ufw --force enable`
    `sudo ufw allow 80/tcp`
    `sudo ufw allow 22`
    `sudo ufw allow 2222`


Install Docker

    `sudo apt-get install docker-ce docker-ce-cli containerd.io -y`
    
    
Volume für nginx erstellen und Nginx aktivieren und Port festlegen    
    
    `docker volume create nginx_data`
    `docker run --name some-nginx -d -p 80:80 nginx`


Vagrant Config Ende
    
    `SHELL`
    `end`

<a name="anleitung"></a>
## Anleitung
Das Aufsetzen der VM ist sehr simpel. Als erstes muss das Repository heruntergeladen werden. Dies wird mit folgendem Befehl gemacht:
    
    `git clone https://github.com/misterT187/M300-Services.git`

Als nächstes öffnet man eine GIT-Bash im Folder M300-Services/lb2
Anschliessend muss nurnoch der Befehl `vagrant up` ausgeführt werden.

<a name="testen"></a>
## Testen
Um zu Testen ob das erstellen der vm mithilfe von Vagrant funktioniert hat, muss im Browser die seite localhost:100 aufgerufen werden. 
Wenn folgende Seite zusehen ist hat alles funktioniert.

![nginx-webserver](https://github.com/misterT187/M300-Services/blob/main/lb2/images/nginx.PNG)

<a name="quellenverzeichnis"></a>
## Quellenverzeichnis

- Apache: (https://httpd.apache.org/)  
- Markdown: (https://www.markdownguide.org/cheat-sheet/)
- Vagrant: (https://gist.github.com/wpscholar/a49594e2e2b918f4d0c4)