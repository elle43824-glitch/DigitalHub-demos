# DigitalHub — Demo dal vivo

Sito statico con le demo dei tutorial del canale **DigitalHub**:

- `index.html` — pagina iniziale con i due demo
- `slime-cannon.html` — il cannone di slime (HTML + JavaScript, nessuna libreria)
- `prima-pagina.html` — l'esempio del Corso HTML Parte 1
- `assets/slime.png` — immagine usata da `prima-pagina.html`

## Pubblicare con GitHub Pages (gratis, 5 minuti)

1. Crea un account su [github.com](https://github.com) (se non lo hai).
2. **New repository** → nome: `digitalhub-demos` → visibilità **Public** → *Create repository*.
3. **Add file → Upload files** → trascina **tutto il contenuto di questa cartella**
   (inclusi `assets/`, `.nojekyll`, `index.html`, i due HTML).
4. **Commit changes**.
5. **Settings** → **Pages** → *Build and deployment*:
   - Source: **Deploy from a branch**
   - Branch: **main**, cartella **/(root)** → **Save**
6. Aspetta 1–2 minuti, poi apri:

```
https://TUONOMEUTENTE.github.io/digitalhub-demos/
```

Link diretto al cannone:

```
https://TUONOMEUTENTE.github.io/digitalhub-demos/slime-cannon.html
```

> Il link è **HTTPS** e funziona da telefono e computer. Non serve un server.

## È sicuro?

Sì, per questi motivi:

- è un sito **statico**: nessun server, nessun database, nessun login;
- **non raccoglie dati**: niente cookie, niente analytics, niente form;
- **non carica risorse esterne**: tutto dentro i file;
- GitHub fornisce **HTTPS** automatico.

Cosa tenere presente:

- il codice è **pubblico**: chiunque può leggerlo e copiarlo (per un tutorial è un vantaggio);
- **non caricare** dati personali, indirizzi, email private o chiavi API;
- il repository **deve essere pubblico** per usare Pages con l'account gratuito.

## Alternative senza rendere pubblico il codice

| Servizio | Come funziona | Note |
|---|---|---|
| **Netlify Drop** | trascini la cartella su app.netlify.com/drop | gratis, URL tipo `nome.netlify.app`, repo può restare privato |
| **Cloudflare Pages** | carichi la cartella o colleghi un repo privato | gratis, molto veloce |
| **Vercel** | importi il repo (anche privato) | gratis per progetti personali |

## Aggiornare il sito

Modifichi un file → **Add file → Upload files** (o trascini la nuova versione) → **Commit**.
Dopo ~1 minuto il sito è aggiornato: **il link non cambia**.

## Condividere con il pubblico

- **Descrizione di YouTube**: metti il link del cannone + il link della pagina iniziale
- **Commento fissato**: “▶ Prova la demo qui: …”
- **Community post** e **Short**: link in descrizione
- **QR code**: genera un QR del link per lezioni in aula o slide

---

## Impostazioni: cosa serve davvero?

### Visitatore non può modificare niente (per design)

GitHub Pages è **hosting statico**: i visitatori ricevono una copia dei file e li
eseguono nel **loro** browser. Non esiste alcun canale per scrivere nel repository.

| Cosa può fare un visitatore | Cosa NON può fare |
|---|---|
| aprire le pagine e usare le demo | modificare, cancellare o caricare file |
| scaricare i file (come qualsiasi sito web) | accedere al tuo account GitHub |
| condividere il link | creare problemi al sito o al repository |

Le uniche azioni possibili per modificare i file le hai **tu** dal tuo account.

### Impostazioni consigliate (5 minuti, una volta sola)

**1. Proteggi il tuo account (la cosa più importante)**
- Settings (del profilo) → **Password and authentication** → attiva **2FA**
- Usa una password unica e lunga

**2. Repository → Settings → General → Features**
- togli la spunta a **Issues**, **Discussions**, **Wiki**, **Projects**
  (non servono per un sito di demo e riducono la superficie di disturbo)

**3. Repository → Settings → Branches**
- *Add branch protection rule* → branch `main` → attiva **Require a pull request**
  (utile se un giorno collabori con qualcuno: nessuno può scrivere direttamente su `main`)

**4. Non mettere mai dati sensibili**
- niente email private, numeri, chiavi API, file `.env`
- se per errore carichi una chiave: **revocala subito** sul servizio che l'ha emessa

**5. Se un giorno aggiungi un modulo di contatto**
- non usare token nel codice (sarebbero pubblici)
- usa un servizio esterno che gestisce l'invio lato server (es. Formspree, Netlify Forms)

### Limiti di GitHub Pages (account gratuito)

- repository **pubblico** (con repo privato serve GitHub Pro)
- sito fino a **1 GB**, circa **100 GB/mese** di traffico, **10 build/ora**
- solo file statici: niente PHP, Node, database

Per due demo con qualche visita al giorno non ci si avvicina minimamente ai limiti.

### Cosa è già incluso in questa cartella

| File | A cosa serve |
|---|---|
| `.nojekyll` | evita l'elaborazione Jekyll: pubblica i file così come sono |
| `404.html` | pagina di errore personalizzata con ritorno alle demo |
| `robots.txt` | permette l'indicizzazione (utile per la visibilità) |
| `LICENSE` | licenza CC BY 4.0: chi riusa il codice deve citare DigitalHub |

### Verifica già fatta sui file

- **nessuna** chiamata di rete (`fetch`, `XMLHttpRequest`, `WebSocket`)
- **nessun** salvataggio dati (`localStorage`, `sessionStorage`, cookie)
- **nessuna** risorsa esterna caricata: solo link cliccabili verso YouTube
- **nessun** `eval` o codice dinamico
