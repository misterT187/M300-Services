# M300 LB3
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

<a name="anleitung"></a>
## Anleitung
Das Aufsetzen der VM ist sehr simpel. Als erstes muss das Repository heruntergeladen werden. Dies wird mit folgendem Befehl gemacht:
    
    `git clone https://github.com/misterT187/M300-Services.git`

Als nächstes öffnet man eine GIT-Bash im Folder M300-Services/lb3
Anschliessend muss nurnoch der Befehl `vagrant up` ausgeführt werden.

<a name="testen"></a>
## Testen
Um zu Testen ob das erstellen der vm mithilfe von Vagrant funktioniert hat, muss im Browser die seite localhost:100 aufgerufen werden. 
Wenn folgende Seite zusehen ist hat alles funktioniert.

![nginx-webserver](https://github.com/misterT187/M300-Services/blob/main/lb2/images/nginx.PNG)

<a name="quellenverzeichnis"></a>
## Quellenverzeichnis
