# Kryptographische Methoden für die IT


## Kurzübersicht

* Voraussetzungen
* Eigenschaften
* Verwendung

## Voraussetzungen

* Veracrypt
* Ubuntu 20.04 oder 22.04
* dm-Crypt/cryptsetup/luks

## Eigenschaften

### Veracrypt

> VeraCrypt wurde als völlig kostenlose Sicherheitssoftware entwickelt, ein Open-Source-Dienstprogramm, das in der Lage sein wird, die Aufgabe der Festplatten- oder Dateiverschlüsselung auszuführen, und ist ein Tool, das für Windows-, MacOS- und Linux-Betriebssysteme verfügbar ist. Mit VeraCrypt wird es möglich sein, alle unsere Dateien zu schützen, indem wir sie mit einem Passwort verschlüsseln, das dafür verantwortlich ist, einen geschützten Bereich lokal oder auf einem Speichergerät namens Volume zu erstellen, all dieses Volume wird in einem Container namens Container gehostet, der geöffnet wird (Einhängen) und Schließen (Auswerfen) in einer einzigen Datei. Mit VeraCrypt wird es möglich sein, bestimmte Aufgaben auszuführen, wie zum Beispiel:

* Outer Volume: 
> Es ist die einfachste Form von VeraCrypt, die verschlüsselte Volumes verwendet, bei denen es sich um Ordner handelt, die mit starken Passwörtern erstellt wurden, sodass sie nur zugänglich sind, wenn sie als virtuelle verschlüsselte Festplatte gemountet werden, die wie wir als echte Festplatte gemountet wird.

* Hidden Volume
> Ein verstecktes verschlüsseltes Volume ist eine Funktion bestimmter Verschlüsselungssysteme, die es ermöglicht, zwei Schlüssel für ein Volume zu erstellen; ein Schlüssel entschlüsselt den wahren Inhalt (verborgenes Volumen) und der andere Schlüssel (der „Notfallschlüssel“) entschlüsselt einige vorarrangierte unschuldige Inhalte (Cover-Volume). Wir können dann den inneren oder „versteckten“ Container erstellen und ihm ein anderes Passwort geben. Für jeden, der den äußeren Behälter inspiziert, gibt es keine Möglichkeit zu erkennen, dass es sich um einen versteckten Behälter handelt.

## Umsetzung 1) Veracrypt


> Zunächst muss die Veracrypt-Installation erfolgen. Wir können es auf jedem Ubuntu- oder Kali-Betriebssystem installieren.

![1](https://user-images.githubusercontent.com/59235025/193424724-b586c756-5000-47de-ba04-7b8b902bee0e.PNG)

> Anschließend wird die heruntergeladene Zip-Datei nach dem Entpacken im Terminal geöffnet. Und die Erklärung wird akzeptiert.

![3](https://user-images.githubusercontent.com/59235025/193424747-041036c1-4a06-4ec8-92e0-9d37be10c8e4.PNG)

> Dann öffnet sich die Anwendung und die Verschlüsselung kann gestartet werden.
> 
![5](https://user-images.githubusercontent.com/59235025/193424755-52c80fb2-e9dd-4ef9-8d3d-84f4e59d22f2.PNG)

> Nachdem Sie auf "Create Volume" geklickt haben, wählen Sie im nächsten Abschnitt "Create an encryted file container"  und können wir fortfahren.

![6](https://user-images.githubusercontent.com/59235025/193424764-dcffdb16-d957-45ec-b066-0db13be2d8aa.PNG)

> Hier sollte "Hidden VeraCrypt volume" ausgewählt werden.

![7](https://user-images.githubusercontent.com/59235025/193424774-672701b8-d8eb-47a6-819d-72da5d7d8a56.PNG)

> Der Standort wird festgelegt.

![8](https://user-images.githubusercontent.com/59235025/193424781-eae4b155-4b6a-418f-9e9c-2c343a559643.PNG)

> Nach Angabe der notwendigen Parameter wird fortgefahren.

![9](https://user-images.githubusercontent.com/59235025/193424799-46eefecc-cfdb-43f2-a4ac-fdf5bfd46a27.PNG)

![10](https://user-images.githubusercontent.com/59235025/193424810-36a2fcc9-2949-451d-b55d-42f03d800321.PNG)

> dann wird als Passwort der "Vorname" angegeben.

![11](https://user-images.githubusercontent.com/59235025/193424827-06ec3d09-c9e8-4d6f-9d90-8e35c16e53b7.PNG)

> Als Dateisystem ist FAT ausgewählt.

![12](https://user-images.githubusercontent.com/59235025/193424840-0705412a-8191-468f-8347-49ef18b51ea4.PNG)

> Im nächsten Teil müssen Mausbewegungen ausgeführt werden, damit die Operation stattfindet.

![13](https://user-images.githubusercontent.com/59235025/193424849-6a7ab8ce-d6f0-4d36-9d2a-2a9e2c069694.PNG)

> Nachdem die Formatierung abgeschlossen ist, können Sie zum Abschnitt "Hidden volume" wechseln.

![14](https://user-images.githubusercontent.com/59235025/193424864-17d2901a-e998-46a3-ae8a-f52d580e196a.PNG)

> Nach Angabe der notwendigen Parameter im Bereich Hidden sollte Keyfile.png als zusätzliches Passwort angegeben werden.

![15](https://user-images.githubusercontent.com/59235025/193424876-be97cef5-af7a-4522-b682-64703bc01307.PNG)
> In diesem Abschnitt wird als Passwort „Nachname“ eingetragen.

![16](https://user-images.githubusercontent.com/59235025/193424883-92382a3b-a221-4d91-8309-01f073d3c426.PNG)
> Nach Angabe von PIM und Filesystem in weiteren Parametern kann das Format gestartet werden.

![17](https://user-images.githubusercontent.com/59235025/193424886-51765de5-a66b-4798-9dc6-73fe8edd002d.PNG)
![18](https://user-images.githubusercontent.com/59235025/193424891-a260c5ac-8053-43db-8832-e4e8fb0123c1.PNG)
![19](https://user-images.githubusercontent.com/59235025/193424894-2a4381f4-59ea-4a51-9793-61795f41ac95.PNG)
![20](https://user-images.githubusercontent.com/59235025/193424898-db2c860b-88ca-4604-a127-f5d20cd29f52.PNG)

## Umsetzung 2) dm-crypt

> Die Laufwerksverwaltung wird im Ubuntu-System geöffnet.

![1](https://user-images.githubusercontent.com/59235025/193424906-7bae5038-c06a-4b73-8b9b-57cbbe7ee3f3.PNG)

> Wählen Sie "Format Partition", indem Sie mit der rechten Maustaste auf die ermittelte Festplatte klicken

![2](https://user-images.githubusercontent.com/59235025/193424914-d51d2433-68c6-492d-b3d3-150d9201e692.PNG)

> Der Name wird vergeben und „Erase“ und andere Teile werden ausgewählt.

![3](https://user-images.githubusercontent.com/59235025/193424925-b5c61dab-a4a1-485e-b2b6-276e0f1d37a1.PNG)

> Dann es wird ein passendes Passwort vergeben.

![4](https://user-images.githubusercontent.com/59235025/193424933-0bff3bc3-2979-4320-a6df-5bd1b6da4f1b.PNG)

> Wie Sie unten sehen können, ist der Verschlüsselungsprozess abgeschlossen.

![5](https://user-images.githubusercontent.com/59235025/193424951-2e81b82f-3aa3-4b44-9622-ec7746302476.PNG)

> Wenn es gemountet werden soll, kann dies erfolgen, ohne nach einem Passwort zu fragen.

![6](https://user-images.githubusercontent.com/59235025/193424956-10722bf2-574f-47b7-b7fd-2e5be429ec38.PNG)

> Wie man im Bild sehen kann, wird die Partition beim Systemstart automatisch ohne Benutzereingriff gemountet.

![7](https://user-images.githubusercontent.com/59235025/193424960-cc374360-e535-44fd-88cf-b96bcf993dd8.PNG)

![Inked3](https://user-images.githubusercontent.com/59235025/193424973-5a72dac7-1cb8-4fb7-b1bb-c15719a68570.jpg)
