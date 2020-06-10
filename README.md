# SystemsDesign_Storage - Unterschied zwischen Speichern in Memory und Speichern on Disk

Mit diesem kleinen Beispiel soll der Unterschied zwischen Speicherung in Memory und on Disk veranschaulicht werden. Die Speicherung in Memory geht verloren nachdem der Server abgestürzt ist. Auf Daten on Disk kann auch nach dem Absturz des Servers zugegriffen werden. Die Vorteile der Speicherung on Disk sind eindeutig, jedoch kann die Speicherung in Memory Zeitvorteile bringen und deshalb an manchen Stellen im System sinnvoll sein.

## Memory
### Schritt 1 - Server starten
Öffne das Terminal, navigiere in den Ordner mit den Files und tippe "node server.js"

### Schritt 2 - Speicher in Memory mit POST
Öffne ein weiteres Terminal, navigiere in den gleichen Ordner und tippe ... curl localhost:3001/memory/foo --header 'Content-Type: application/json' --data '{"data": "This is some data in memory."}'

### Schritte 3 - Memory einsehen
Öffne ein weiteres Terminal, navigiere in den gleichen Ordner und tippe ... curl localhost:3001/memory/foo -w "\n"

### Schritt 4 - Server schliessen und wieder starten
Command+C, um den Server abzustürzen; Schritt 1 wiederholen

### Schritt 5 - Schritt 3 wiederholen

### Fazit
Daten in Memory gehen verloren

## Disk
Wiederhole die Schritte von Memory mit folgenden Anpassungen:
Schritt 2: curl localhost:3001/disk/foo --header 'Content-Type: application/json' --data '{"data": "This is some data in disk."}'
Schritt 3: curl localhost:3001/disk/foo -w "\n"

### Fazit
Daten on Disk gehen nicht verloren
