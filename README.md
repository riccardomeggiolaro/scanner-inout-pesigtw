# IN-OUT / PESI-GTW Scanner

Utility grafica (Tkinter) che scansiona la rete locale alla ricerca dei dispositivi
che eseguono **IN-OUT** o **PESI-GTW**.

Per ogni host della sottorete viene chiamato `GET http://<ip>/whoami`; il dispositivo
viene riconosciuto se risponde con:

```json
{"program_name": "in-out"}
```

oppure

```json
{"program_name": "pesi-gtw"}
```

Nella lista dei risultati compaiono IP e programma; doppio click per aprire
l'interfaccia web del dispositivo.

## Avvio da sorgente

```bash
pip install -r requirements.txt
python3 scanner.py
```

## Eseguibili

- `debian13/INOUT-Scanner`
- `windows11/INOUT-Scanner.zip`
- `INOUT-Scanner.zip`

Nota: gli eseguibili sono stati compilati prima dell'aggiunta del supporto
PESI-GTW e vanno ricompilati, ad esempio:

```bash
pip install pyinstaller
pyinstaller --onefile --windowed --name INOUT-Scanner scanner.py
```
