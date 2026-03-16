# IP/Domain Analyzer - Multi-API Security Analysis Tool

Strumento di analisi sicurezza per IP e domini utilizzando AbuseIPDB, VirusTotal e Shodan.

## 🚀 Caratteristiche

- ✅ Interfaccia grafica intuitiva
- ✅ Supporto per analisi singola o multipla
- ✅ Integrazione con 3 API di sicurezza principali
- ✅ Esportazione risultati
- ✅ Caricamento da file
- ✅ Risultati colorati e ben formattati
- ✅ Analisi in background con barra di progresso

## 📋 Requisiti

- Python 3.7 o superiore
- WSL (Windows Subsystem for Linux) se su Windows
- Connessione internet

## 🔧 Installazione

### Su WSL/Linux:

1. **Installa Python e pip** (se non già installati):
```bash
sudo apt update
sudo apt install python3 python3-pip python3-tk -y
```

2. **Installa le dipendenze Python**:
```bash
pip3 install requests
```

3. **Rendi il file eseguibile**:
```bash
chmod +x ip_analyzer.py
```

## ▶️ Avvio del Programma

### Da WSL:

```bash
python3 ip_analyzer.py
```

oppure:

```bash
./ip_analyzer.py
```

### Nota per WSL:
Se hai problemi con l'interfaccia grafica in WSL, assicurati di avere un X server installato su Windows (come VcXsrv o Xming) e che la variabile DISPLAY sia configurata:

```bash
export DISPLAY=:0
```

Oppure aggiungi al tuo `~/.bashrc`:
```bash
echo 'export DISPLAY=:0' >> ~/.bashrc
source ~/.bashrc
```

## 📖 Come Usare

### 1. Inserimento IP/Domini

- **Manualmente**: Inserisci IP o domini nella casella di testo a sinistra (uno per riga)
- **Da File**: Clicca "📁 Carica da File" e seleziona un file .txt o .csv

Esempi:
```
8.8.8.8
1.1.1.1
malicious-site.com
example.com
192.168.1.1
```

### 2. Selezione API

Seleziona quali API utilizzare per l'analisi:
- ☑️ AbuseIPDB
- ☑️ VirusTotal
- ☑️ Shodan

### 3. Esecuzione Analisi

- **🔍 Analizza Singolo IP/Dominio**: Analizza solo il primo elemento della lista
- **🔍 Analizza Tutti**: Analizza tutti gli IP/domini inseriti

### 4. Visualizzazione Risultati

I risultati appaiono nel pannello destro con codifica a colori:
- 🟢 **Verde**: Basso rischio / Sicuro
- 🟡 **Giallo**: Rischio medio / Sospetto
- 🔴 **Rosso**: Alto rischio / Malevolo

### 5. Esportazione

Clicca "💾 Esporta Risultati" per salvare l'analisi in un file di testo.

## 🔍 Informazioni Fornite

### AbuseIPDB
- Abuse Confidence Score (0-100%)
- Numero di report
- Paese e ISP
- Tipo di utilizzo
- Whitelist status

### VirusTotal
- Analisi malware (numero di detection)
- Reputazione
- Categorie
- Statistiche complete (malevolo, sospetto, innocuo)

### Shodan
- Porte aperte
- Servizi attivi
- Vulnerabilità note (CVE)
- Informazioni geolocalizzazione
- Organizzazione e ISP
- Hostnames

## 📝 Formato File di Input

Il programma accetta file di testo con IP/domini separati da newline:

```
8.8.8.8
google.com
1.1.1.1
facebook.com
185.220.101.1
```

## 🔐 Note sulla Sicurezza

- Le API key sono già integrate nel codice
- Tutte le richieste utilizzano HTTPS
- I risultati possono essere sensibili - gestirli con cura
- Non condividere risultati contenenti informazioni sensibili

## ⚠️ Limitazioni

- **Rate Limiting**: Le API hanno limiti di richieste
  - AbuseIPDB: ~1000 richieste/giorno (piano gratuito)
  - VirusTotal: ~500 richieste/giorno (piano gratuito)
  - Shodan: ~100 richieste/mese (piano gratuito)
- Shodan funziona solo con indirizzi IP, non domini
- VirusTotal potrebbe non avere informazioni su IP/domini recenti

## 🐛 Risoluzione Problemi

### Errore "ModuleNotFoundError: No module named 'tkinter'"
```bash
sudo apt install python3-tk
```

### Errore "Can't connect to display"
Installa e configura un X server (VcXsrv/Xming) e imposta:
```bash
export DISPLAY=:0
```

### Errore API (401, 403)
- Verifica che le API key siano corrette
- Controlla di non aver superato i limiti di richiesta
- Verifica la connessione internet

### Timeout
- Alcuni IP potrebbero richiedere più tempo
- Aumenta il timeout nella funzione o riprova

## 📧 Support

Per problemi o domande, verifica:
1. Le dipendenze sono installate correttamente
2. Le API key sono valide
3. La connessione internet è attiva
4. Non hai superato i limiti delle API

## 📄 Licenza

Questo strumento è fornito "as is" per scopi educativi e di ricerca sulla sicurezza.

## 🔄 Versione

**v1.0.0** - Release iniziale

---

**Happy Analyzing! 🔍🛡️**
