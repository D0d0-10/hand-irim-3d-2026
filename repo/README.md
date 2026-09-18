# Trustworthy Manipulation — sito del workshop (I-RIM 3D 2026)

Sito statico a **una sola pagina** (`index.html`, HTML+CSS+JS inline, nessuna dipendenza da
Jekyll/Ruby/Node) con i contenuti del vostro proposal per il workshop *"Trustworthy
Manipulation: Closing the Loop Between Humans, AI Models aNd the Physical WorlD"* — in
sigla **HAND**. Nel titolo dell'hero le lettere H/A/N/D sono evidenziate in arancione
per far leggere l'acronimo a colpo d'occhio.

Palette e impaginazione sono ispirate al sito di riferimento che avete indicato
([IARL2026 / IROS2026-workshop](https://aistairc.github.io/IROS2026-workshop/)), ma
riadattate in una singola pagina più semplice da mantenere (niente build step: è tutto in
un file).

---

## 1. Come vederla subito (debug locale)

Tre modi, dal più semplice al più comodo per editare in tempo reale:

**A — Aprila e basta**
Fai doppio clic su `index.html`: si apre nel browser di default. Funziona perché tutto
(CSS, JS, font) è nello stesso file o caricato da CDN — non servono server o build.

**B — Server locale (consigliato se poi aggiungete immagini/altre pagine)**
```bash
cd cartella-del-sito
python3 -m http.server 8000
```
poi apri `http://localhost:8000` nel browser. Necessario se in futuro aggiungete file
locali (foto, un secondo file HTML) referenziati con percorsi relativi, perché alcuni
browser bloccano il caricamento di risorse locali aperte con `file://`.

**C — VS Code + estensione "Live Server"**
Tasto destro su `index.html` → *Open with Live Server*: si apre nel browser e si
aggiorna da solo ogni volta che salvi. È il flusso più comodo mentre riempite le varie
sezioni.

---

## 2. Come pubblicarla su GitHub Pages

1. Create un nuovo repository su GitHub (es. `trustworthy-manipulation-irim2026`), pubblico.
2. Copiate `index.html` (e questo `README.md`, opzionale) nella root del repository.
3. Fate commit e push su GitHub.
4. Nel repository: **Settings → Pages**.
5. Sotto "Build and deployment" → Source: **Deploy from a branch**. Branch: **main**,
   cartella **/(root)**. Salvate.
6. Dopo 1-2 minuti la pagina sarà live su
   `https://<vostro-utente-o-org>.github.io/<nome-repo>/`.

Non serve `_config.yml`, Gemfile o altro: essendo un solo file HTML statico, GitHub Pages
lo serve così com'è (con o senza l'elaborazione Jekyll di default, che comunque lascia
intatto un file `.html` senza front matter come questo).

Per aggiornamenti futuri: modificate `index.html`, fate commit e push — GitHub Pages
ripubblica automaticamente in circa un minuto.

---

## 3. Cosa riempire ancora (placeholder da aggiornare)

Cercate nel file la stringa `EDIT:` nei commenti HTML: segnano ogni punto compilato con
dati provvisori o mancanti nel proposal. In sintesi:

| Sezione | Cosa manca | Dove |
|---|---|---|
| Call for Abstracts | Link reale a EasyChair | bottone "Submit on EasyChair →" |
| Info importanti | Scadenza per l'invio degli extended abstract | card "Submission deadline" |
| Info importanti | Orari e logistica dettagliati (per ora solo "90 minutes") | card "Duration" |
| Speakers | Titolo dei talk (per ora "to be announced" per tutti, su vostra richiesta) | ogni card speaker |
| Speakers | Foto reali per Secchi, Ajoudani, Di Palo, Di Stefano (vedi sotto) | avatar con iniziali |
| Footer | Link al repository GitHub una volta pubblicato | colonna "Elsewhere" |

**Foto dei relatori:** la cartella `assets/img/` è già inclusa, con la foto di Mario
Selvaggio (`mario-selvaggio.jpg`) già collegata alla sua card. Per gli altri speaker,
che per ora usano avatar con iniziali generati via CSS:
1. Aggiungete la foto in `assets/img/` (es. `cristian-secchi.jpg`), meglio se già
   quadrata — questo sito la ritaglia in cerchio ma non la ricompone, quindi partite da
   un'immagine centrata sul volto.
2. Al posto di `<div class="avatar" style="background:...">CS</div>` mettete
   `<img class="avatar" src="assets/img/cristian-secchi.jpg" alt="Cristian Secchi">`.

---

## 4. Struttura del contenuto

Un'unica pagina con sezioni ancorate (la nav in alto scorre alle sezioni):

- **Hero** — titolo con acronimo HAND evidenziato, tag conferenza, diagramma del "loop"
  (Humans → AI Models → Physical World, con i tre pilastri Recovery / Robustness /
  Verification presi dal proposal).
- **About** — testo di framing + i 4 obiettivi del workshop + keyword.
- **Topics** — i 4 topic del proposal, colorati secondo il pilastro a cui corrispondono.
- **Speakers** — i 5 relatori confermati, con nota sul formato dei talk (12–15 min +
  panel 20–30 min con Slido); i titoli dei talk sono segnati "to be announced" in
  attesa che li forniate.
- **Info importanti** — solo data, durata, sede, formato submission e scadenza (su
  vostra richiesta, senza le card Format/Expected participants/Contact/Official updates).
- **Call for Extended Abstracts** — linee guida e canali di disseminazione.
- **Organizers** — i 5 organizzatori con email.
- **Outcomes & follow-up** — white paper, special issue su IEEE RAM, seconda edizione a
  IROS 2027, registrazione.

---

## 5. Nota sulla pagina ufficiale

Nel proposal indicate che la pagina ufficiale del workshop sarà ospitata sul sito del
[BRAIR Lab](https://www.santannapisa.it/en/institute/biorobotics/brair-lab). Questa
pagina GitHub può funzionare da sito "satellite" per la promozione social (link facile
da condividere, aggiornabile in autonomia) mentre quella resta la fonte ufficiale — o,
se preferite, potete linkarla direttamente dalla pagina del BRAIR Lab una volta pubblicata.
