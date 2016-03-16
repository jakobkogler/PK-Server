# Verbinden mit dem PK-Server

Die Adresse vom Server ist: `antigone.inflab.tuwien.ac.at`, Benutzername ist `p<Matrikelnummer>` und das Passwort habt ihr heute in der Übung angelegt. 

Falls jemand noch kein Passwort angelegt hat, oder das Passwort ändern will, kann man das unter  [password.inflab.tuwien.ac.at](http://password.inflab.tuwien.ac.at/) erledigen. 

Ich stelle hier kurz zwei Methoden vor, wie man sich mit dem Server verbindet. 

## Mit ssh und scp

Diese Methode ist hauptsächlich für Linux-User gedacht. Sollte aber auch unter Mac und Windows funktionieren. Unter Windows heißen die Befehle eventuell ein wenig anders. 

Über das Terminal kann man sich via `ssh` mit dem Server verbinden und dort durch die Ordnerstruktur navigieren. 

    $ ssh p<Matrikelnummer>@antigone.inflab.tuwien.ac.at
    p<Matrikelnummer>@antigone.inflab.tuwien.ac.at's password: 
    $ ls
    Aufgaben  bin  Desktop  README
    $ ls Aufgaben
    Aufgabenblatt0  Aufgabenblatt1
    $ ls Aufgaben/Aufgabenblatt1
    Aufgabe1  Aufgabe2  Aufgabe3  Aufgabe4  Aufgabe5
    $ exit
    logout
    Connection to antigone.inflab.tuwien.ac.at closed.
    
Kopieren funktioniert via `scp`. 

    $ mkdir Aufgabenblatt1
    $ scp -r p<Matrikelnummer>@antigone.inflab.tuwien.ac.at:Aufgaben/Aufgabenblatt1/* Aufgabenblatt1/

Und nach dem Lösen der Aufgaben kann man die Beispiele wieder auf den Server laden. 

    $ scp -r Aufgabenblatt1/* p<Matrikelnummer>@antigone.inflab.tuwien.ac.at:Aufgaben/Aufgabenblatt1/

Natürlich kann man die Beispiele auch direkt auf dem Server bearbeiten. Nachdem man eine Verbindung mit dem Server aufgebaut hat, kann man dort Editoren wie `vim`, `emacs`, ... benutzen und die Beispiele anschließend mit `javac` bzw. `java` testen. 

## Mit einem SFTP Programm wie WinSCP

Hauptsächlich für Windows-Benutzer, die gerne mit GUIs arbeiten. 
Downloaden kann man WinSCP unter [https://winscp.net](https://winscp.net/). 

Nach dem Installieren kommt man zu einem Fester wie diesem: 

![WinSCP-Connection Window](https://github.com/jakobkogler/PK-Server/blob/master/WinSCP_connect.png)

Und nach dem Eingaben der Server-Adresse, des Benutzernames und des Passwortes kommt man zu einer solchen Oberfläche: 

![WinSCP-Window](https://github.com/jakobkogler/PK-Server/blob/master/WinSCP_window.png)

Auf der linken Seite sieht man die Ordnerstruktur des eigenen Rechners, auf der rechten Seite die des Servers. Man kann nun z.B. auf dem Server in den Ordner `Aufgaben` wechseln und dort den Ordner `Aufgabenblatt1` downloaden. Man kann auch direkt den Ordner mit Drag and Drop auf die linke Seite ziehen. 

Anschließend, nach dem Lösen der Aufgaben, kann man dann den Ordner von Links wieder nach Rechts schieben. 
Beachtet, dass ihr den Ordner wieder an die selbe stelle kopiert, bzw. den alten Ordner überschreibt.
