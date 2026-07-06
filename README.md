# Il Mio Allenamento — PWA installabile

App offline per visualizzare la scheda, registrare i pesi e vedere l'ultimo allenamento.
Nessun server necessario: dopo la pubblicazione funziona anche senza connessione internet.

## Cosa contiene questa cartella

```
pwa/
├── index.html       ← l'app
├── manifest.json     ← metadati per l'installazione come app
├── sw.js             ← service worker (funzionamento offline)
├── icons/            ← icone dell'app
└── README.md         ← questa guida
```

## Dove salva i dati

Tutto viene salvato nel `localStorage` del browser del telefono: nessun account, nessun
server, nessun costo. Il rovescio della medaglia è che i dati restano su quel browser/telefono.
Usa i pulsanti **"Esporta backup"** (dalla Home dell'app) ogni tanto, specialmente prima di
cambiare telefono o svuotare la cache del browser: scarica un file `.json` che puoi poi
reimportare con **"Importa backup"**.

---

## Come pubblicarla gratis (scegli UNA delle due opzioni)

### Opzione A — GitHub Pages (consigliata, 100% gratis)

1. Crea un account su [github.com](https://github.com) se non ce l'hai già.
2. Crea un nuovo repository (es. chiamalo `allenamento`), pubblico.
3. Carica tutti i file di questa cartella `pwa/` nel repository:
   - dalla pagina del repository su github.com, clicca **"Add file" → "Upload files"**
   - trascina dentro tutti i file (index.html, manifest.json, sw.js, la cartella icons/, README.md)
   - clicca **"Commit changes"**
4. Vai su **Settings → Pages** (menu a sinistra del repository).
5. In "Source" scegli il branch `main` e cartella `/ (root)`, poi **Save**.
6. Dopo 1-2 minuti, GitHub ti darà un link tipo:
   `https://tuonomeutente.github.io/allenamento/`
7. Apri quel link dal telefono → menu del browser → **"Aggiungi a schermata Home"**.

Da quel momento è un'app vera: icona sulla home, si apre a schermo intero, funziona offline.

### Opzione B — Netlify (drag & drop, ancora più rapido)

1. Vai su [app.netlify.com/drop](https://app.netlify.com/drop)
2. Trascina l'intera cartella `pwa/` nella pagina
3. Netlify pubblica subito e ti dà un link (es. `https://nome-a-caso.netlify.app`)
4. Apri il link dal telefono → **"Aggiungi a schermata Home"**

Con un account Netlify gratuito puoi anche rinominare il sito e aggiornarlo in futuro
ricaricando la cartella.

---

## Aggiornare l'app in futuro

Se in futuro vuoi modificare la scheda (nuovi esercizi, altre note), basta editare
`index.html` (cerca l'oggetto `SCHEDE` all'inizio dello `<script>`) e ricaricare i file
sull'hosting scelto. I dati già salvati sul telefono non vengono toccati.
