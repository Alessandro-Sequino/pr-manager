# PR Manager 🎭

> Gestionale per PR di locali notturni e organizzatori di eventi.  
> Gruppi clienti, acconti, check-in ospiti e pacchetti — tutto in un singolo file, senza installazioni.

![Versione](https://img.shields.io/badge/versione-1.0.0-C9A84C?style=flat-square)
![Zero dipendenze](https://img.shields.io/badge/dipendenze-zero-4ECDA4?style=flat-square)
![Stack](https://img.shields.io/badge/stack-HTML%20%2F%20CSS%20%2F%20JS-4FA3E8?style=flat-square)
![Offline](https://img.shields.io/badge/offline--ready-✓-4ECDA4?style=flat-square)
![Licenza](https://img.shields.io/badge/licenza-MIT-lightgrey?style=flat-square)

---

<!-- Sostituisci con uno screenshot reale dell'app una volta pubblicata su GitHub Pages -->
> 📸 **Demo live →** [tuo-username.github.io/pr-manager](https://tuo-username.github.io/pr-manager)

---

## Perché esiste

I PR di locali gestiscono ogni sera decine di gruppi, tracciano acconti verbali, compilano liste ospiti su carta o su fogli Excel non pensati per questo lavoro. PR Manager risolve esattamente questo: uno strumento costruito sul flusso di lavoro reale di un PR, usabile da smartphone in serata senza account, senza server, senza abbonamenti.

---

## Funzionalità

### Dashboard
Panoramica istantanea con metriche configurabili: totale incassato, incasso confermato, crediti da saldare, eventi attivi, ultimi acconti e prossimi eventi.

### Gruppi
Archivio clienti con lista membri, numeri di telefono, storico acconti e saldo residuo per gruppo. I gruppi sono riutilizzabili su più eventi e importabili direttamente nelle liste ospiti.

### Acconti
Tracciamento pagamenti con stati (confermato / in attesa / scaduto) e calcolo automatico del saldo residuo. Alert visivo per importi non ancora saldati.

### Eventi
Gestione calendario eventi con riepilogo incassi, numero ospiti attesi e dettaglio per singolo evento. Vista settimanale e lista con filtro per stato.

### Statistiche
Grafici e tabelle su incassi per periodo, performance per gruppo, confronto tra eventi.

### Pacchetti
Creazione e gestione di pacchetti/tavoli con prezzo base, disponibilità e prenotazioni collegate. I pacchetti appaiono anche nella dashboard come riepilogo rapido.

### Liste Ospiti
Check-in in tempo reale con orario di ingresso, marcatura VIP, gestione no-show, ricerca per nome. Import diretto da un gruppo esistente. Export in CSV per ogni evento.

### Impostazioni
Personalizzazione delle metriche visibili in dashboard, valuta, campi opzionali nei moduli. Backup completo dei dati in JSON e ripristino da file.

---

## Come iniziare

Non c'è nulla da installare.

```bash
# Clona il repository
git clone https://github.com/tuo-username/pr-manager.git

# Entra nella cartella
cd pr-manager

# Apri il file nel browser
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Oppure scarica direttamente il file `index.html` e aprilo con qualsiasi browser moderno (Chrome, Safari, Firefox, Edge).

### Installazione come app (mobile)

1. Apri la demo live su iPhone o Android.
2. Tocca **Condividi → Aggiungi a schermata Home** (iOS) oppure il menu del browser → **Installa app** (Android/Chrome).
3. L'app si apre a schermo intero come un'app nativa.

---

## Stack tecnico

| Layer | Tecnologia |
|---|---|
| Struttura | HTML5 semantico |
| Stile | CSS3 con custom properties (design system completo) |
| Logica | JavaScript ES2020 vanilla, nessun framework |
| Persistenza | `localStorage` (auto-save ad ogni modifica) |
| Tipografia | Playfair Display, DM Sans, DM Mono (Google Fonts) |
| Icone | Tabler Icons via webfont CDN |

---

## Architettura

L'applicazione è un **Single-Page Application contenuta in un unico file HTML** (~3.400 righe). La scelta è intenzionale per il contesto d'uso:

- **Portabilità massima** — si condivide via WhatsApp come qualsiasi file.
- **Zero setup** — nessun Node, nessun server, nessun build tool.
- **Funziona offline** — dopo il primo caricamento non serve connessione.

### Gestione dello stato

Tutta l'applicazione ruota attorno a un oggetto di stato centrale `S`, persistito su `localStorage` con auto-save. Il rendering è imperativo: ogni azione utente aggiorna `S` e chiama `render()`, che ridisegna la sezione attiva.

### Limitazioni note

| Limitazione | Motivo | Impatto pratico |
|---|---|---|
| Dati solo locali | Nessun backend | I dati non si sincronizzano tra dispositivi diversi |
| Nessuna autenticazione | App single-user | Un solo PR per installazione |
| Nessuna collaborazione RT | Nessun WebSocket | Non adatto a team distribuiti |

### Possibili evoluzioni

- [ ] Backend con Supabase per sincronizzazione multi-dispositivo
- [ ] Autenticazione — ogni PR con il proprio account
- [ ] Notifiche push per scadenze acconti
- [ ] Condivisione lista ospiti via link (read-only)
- [ ] PWA manifest completo con service worker per offline garantito

---

## Struttura del repository

```
pr-manager/
├── index.html      # Applicazione completa (HTML + CSS + JS)
└── README.md       # Questa pagina
```

---

## Licenza

[MIT](LICENSE) — libero di usare, modificare e distribuire con attribuzione.

---

*Sviluppato da Alessandro Sequino · [ales.sequino@gmail.com](mailto:ales.sequino@gmail.com)*
