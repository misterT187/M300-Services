# M300-Services
Plattforübergreifende Dienste in ein Netzwerk integrieren

## Autor
Thomas Mägerle

## Inhaltsverzeichnis

- [Einführung](#einfuehrung) 
    - [Git Einrichten](#giteinrichten)
    - [File bearbeiten](#filebearbeiten)
    - [Markdown](#markdown)
    - [Vagrant](#vagrant)
    - [Befehle](#Befehle)
    - [Was ist Nginx?](#wasistnginx)
    - [Was ist UFW](#wasistufw)
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
<a name="filebearbeiten"></a>
### File bearbeiten
Als erstes muss man das Verzeichnis Klonen:
```
git clone https://github.com/c7910m/M300-Services/edit/main/README.md
```
Es wird in das Verzeichnis kopiert, indem man sich momentan in der Shell befindet.

Nun kann man das heruntergeladene File bearbeiten.

Danach kann man das File wieder hochladen:
```
git commit
git push
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
https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf

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

<a name="wasistnginx"></a>
### Was ist Nginx?
Nginx ist eine Webserver-Software welche zusätzlich auch noch Reverse Proxy und E-Mail-Proxy unterstützt.

<a name="wasistufw"></a>
### Was ist UFW?
UFW steht für Uncomplicated Firewall. Sprich es ist einfach eine sehr einfach zu handhabende Firewall.

<a name="netzwerkplan"></a>
### Netzwerkplan

Bei mir sieht die Config so aus:
![image](https://user-images.githubusercontent.com/50829674/110802925-f4d4a980-827e-11eb-94ff-dd1340fee389.png)

