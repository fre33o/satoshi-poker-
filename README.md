# Real Life Satoshi Poker Cashgame Texas Holdem
<br></br>

***Vorrausetzungen:***
<br></br>
-	Eine laufende Lightning Node im Tor Netz
-	LNbits installiert auf der Node
-	Wallet of Satoshi
-	Blue Wallet
-	Pokertisch oder Unterlage
-	Pokerchips
-	Pokerkarten
-	Genug Bier, hartes und reale Freunde als Mitspieler
<br></br>

***Was ist die Idee und wieso die Umsetzung?***
<br></br>
Wir sind eine gemütliche Runde die sich seit Jahrzehnten, Monatlich zum Pokerspielen trifft. Nun haben wir uns gedacht, lasst uns doch die komische Automarke in was Besseres umwandeln, Satoshis.
<br></br>

**In der Automarken Welt läuft es bisher so**
<br></br>
-	Jeder der Spielen möchte zahlt 10 in den Poker Pot
-	Jetzt werden Poker Chips im Gegenwert der eingezahlten 10 aus dem Koffer genommen und man setzt sich an den Tisch
-	Sind die 10 verspielt, kann man sich erneut für 10 einkaufen
<br></br>

***Was passiert also mit den ganzen 10ern:***
<br></br>
-	Auf dem Tisch werden die 10er (in Poker Chips als Gegenwert) immer mehr, wenn die Jungs sich öfter einkaufen. Das Automarken Zeug im Poker Pot wird natürlich mehr
-	Spieler bei denen es am Abend besser läuft, wird der Berg Poker Chips, vor Ihnen, immer größer oder auch wieder kleiner, je nach Poker Skills
<br></br>

***Was passiert am Ende des Abends, wenn alle entscheiden wir machen Schluss für Heute:***
<br></br>
Jeder der noch mit Chips vor sich am Poker Tisch sitzt, erhält den Betrag in Automake aus dem Poker Pot zurück. Was natürlich bedeutet, dass am Ende der komplette Inhalt des Poker Pots unter den übrig gebliebenen Spielern ausgezahlt wird und aufgeht.
<br></br>





# Die Anpassung mit Lightning
<br></br>
Nun war der Plan den buy in und cashout Prozess mit Satoshis über das Lightning Netzwerk zu machen. Wir wollten einfach keine Automarke mehr verwenden, weil öfter mal Vergessen wurde welche abzuheben und mit zu bringen. Schlimmer noch, wenn jemand mit einer 50 auf dem Papier die Frage stellte: „Wer kann den klein machen?“. Ihr merkt, nervig.
<br></br>
Also man nehme eine Node, jeder eine Lightning Wallet (Blue Wallet) und vorbereitete QR Codes für die buy ins (Einzahlungen). Der cashout Prozess wird am Ende erledigt, das ist wirklich kein Aufwand.
<br></br>

***Was wird nun alles benötigt:***
<br></br>
-	Node
-	Jeder Spieler benötigt eine Lightning Wallet auf dem Smartphone (Blue Wallet)
-	LNbits mit angelegter Wallet pro Spieler
-	LNbits mit Wallet für den Poker Pot
-	LNbits mit Wallet für die Satoshi Bank
<br></br>

Wieso LNbits? Weil wir hier QR Codes erstellen können die für die Einzahlungen dauerhaft verwendbar sind. Normal generierte invoices unter Lightning können nur 1x verwendet werden und müssten jedes Mal neu generiert werden.
<br></br>

Eine Verbindung der einzelnen Blue Wallets zu den LNbits Konten, damit alle Transaktionen über die eigene Node laufen können. So läuft das Poker Ökosystem außerhalb von Lightning mit Lightning. Die ganzen ein und Auszahlungen erzeugen keine Gebühren, weil die Sats Technisch auf der Node einfach nur von A nach B hin und her geschoben werden.
<br></br>


# Die Einrichtung
<br></br>
***Die Node (Raspiblitz von Fulmo)***
<br></br>
-	In die Node einloggen
-	Unter Services den „LND LNbits“ aktivieren
<br></br>
![This is an image](https://i.imgur.com/lRV7Zwf.png)
<br></br>

![This is an image](https://i.imgur.com/IQpabLv.png)
<br></br>
-	Nach der Installation erscheint das Tool im Node Menü unter „LNbits Server“
<br></br>
![This is an image](https://i.imgur.com/H54rK7g.png)
<br></br>
-	Mit Enter Starten damit das Login Fenster für TOR angezeigt wird
<br></br>
![This is an image](https://i.imgur.com/iGetJzx.png)
<br></br>



***Die Node ist nun vorbereitet. Jetzt brauchen wir einen TOR Browser in dem das LNbits Tool laufen kann, damit wir die benötigten Wallets aller Spieler einrichten können.***
<br></br>

-	Hier ein gutes Video für die TOR Browser installation von „PrivacyTutor“ auf Youtube https://youtu.be/-Nz4LjPie7M
-	Ist der TOR Browser eingerichtet, öffnen wir die LNbits Webseite wie im Fenster der Node angezeigt unter „TOR Browser Hidden Services address (QR see LCD)“.
Die ewig lange Buchstaben und Zahlen Kombination mit .onion am Ende
-	Nun sind wir über den Tor Browser im LNbits Tool eingeloggt und können alle gewünschten Einstellungen vornehmen
-	Am besten den link des LNbits Tool nochmal irgendwo abspeichern oder im Tor Browser als Favorit anlegen
<br></br>

![This is an image](https://i.imgur.com/570eJcc.png)
<br></br>

***Folgende Einstellungen und Extensions waren für unsere Zwecke nötig***
<br></br>
***Extensions: LNURLp und LndHub***
-	Der LNURLp ist für die festen buy ins. Die können wir hier einrichten
-	Der LndHub ist dafür da, damit jeder Spieler seine Wallet scannen kann um sie auf dem Smartphone in der Blue Wallet verwalten zu können
<br></br>

***LNbits benötigt nun Funds***
<br></br>

Jetzt müssen die Sats einmal aus der Node raus gehen und von außen in LNbits rein gehen. Das liegt daran, weil man von der Node die Sats nicht direkt nach LNbits schicken kann.
<br></br>

Dafür habe ich Wallet of Satoshi verwendet. Die App läuft mit Lightning und on chain gleichzeitig. Man kann hier also beides empfangen.
<br></br>

Also entweder verwendet man jetzt die Sats auf seiner eigenen Node, btc von einer Börse oder das was on chain auf der Node liegt und schickt den gewünschten Betrag an die Wallet of Satoshi.
<br></br>

Den ganzen Batzen Sats, der nun in der WoS liegt, kann nun gebündelt an eine Zentral erstellte Wallet in LNbits gehen. Ich habe neben Poker Pot und den Wallets der Spieler einfach eine Wallet mit dem Namen Poker Bank angelegt.
<br></br>

Sind nun genug Sats auf der LNbits Wallet mit dem Namen Poker Bank, dann können die Spieler nun mit mitgebrachten Automarken, die Sie dir geben, sats aus der Poker Bank erhalten. Die landen dann auf dem jeweiligen LNbits Wallet des Spielers. Das Wallet ist in der Blue Wallet des Spielers integriert und er kann seine Balance sehen.
<br></br>

Will der Spieler sich einkaufen, damit er Chips hat um mitspielen zu können, scant er den QR Code „10er“ und so wandern die Sats seiner Wallet auf den Poker Pot unter LNbits.
<br></br>

Ab an den Tisch mit den Chips, Bier in die Hand und lets Poker.
<br></br>


# Der Cashout Prozess
<br></br>

Der Abend war wieder feucht fröhlich und findet nun ein Ende. Jeder der jetzt noch am Tisch sitzt hat auch Chips vor sich stehen, die er nun vom Tisch nimmt und den Gegenwert an Sats auf seine Wallet erhält.
<br></br>

Er zählt seine Chips und erstellt dem Poker Pot eine invoice. Die wird vom Poker Pot bezahlt und der Spieler hat sein Gewinn in der Wallet.
<br></br>

Und weil es so geil war sehen wir uns nächsten Monat wieder.
<br></br>

Wenn zu irgendeinem Vorgang Fragen sind oder Verbesserungsvorschläge. Einfach in die Kommentare schreiben. Auch Lob und Kritik sind erwünscht. Korrekturen mache ich ebenfalls, wenn Ihr irgendwo Fehler finden solltet.
<br></br>

Grüße euer frieo


