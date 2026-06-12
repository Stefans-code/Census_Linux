# Census ERP — Linux

Build Linux di **Census**, gestionale ERP (fatturazione, magazzino con barcode, scadenzario, statistiche).

A ogni push su `main` la GitHub Action produce due artifact nella tab Actions:

- **Census-Linux-deb** — pacchetto `.deb` installabile (`sudo apt install ./Census_2.0.0_amd64.deb`), con voce nel menu applicazioni e icona
- **Census-Linux-portable** — `tar.gz` portable: estrai ed esegui `./Census/Census`

Build manuale in locale:

```bash
pip install -r requirements.txt pyinstaller
pyinstaller main.py --name Census --windowed \
  --collect-all customtkinter --add-data "icon.png:." --add-data "bg_watermark.png:."
```
