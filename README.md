# 🚴 Guida Setup — Calendario Triveneto Allieve 2026
## GitHub Pages + JSONBin — tempo stimato: ~10 minuti

---

## PARTE 1 — Crea il "database" su JSONBin (5 min)

### 1.1 Crea account su JSONBin
1. Vai su **https://jsonbin.io**
2. Clicca **Sign Up** → registrati (basta email)
3. Conferma l'email

### 1.2 Crea un Bin (il tuo "cassetto dati")
1. Dopo il login, clicca **+ Create Bin**
2. Nel campo contenuto, incolla questo testo minimo:
   ```json
   {"races":[],"availability":{},"users":[]}
   ```
3. Dai un nome al bin: `calendario-triveneto-2026`
4. Clicca **Create** → salva il **BIN ID** che compare nell'URL
   - Es: `https://jsonbin.io/b/` **`6840abcd1234ef56789012`** ← questo è il Bin ID

### 1.3 Copia la tua API Key
1. Vai su **Account** → **API Keys**
2. Copia la **Secret Key** (inizia con `$2b$10$...`)
3. Conservala — ti servirà per connetterti e da dare ai tecnici

### 1.4 Nota i tuoi dati (tienili da parte)
```
Bin ID:  6840abcd1234ef56789012   ← il tuo
API Key: $2b$10$xxxxxxxxxxxxxxxx  ← la tua
```

---

## PARTE 2 — Metti la pagina online con GitHub Pages (5 min)

### 2.1 Crea un repository GitHub
1. Vai su **https://github.com** → login (o crea account)
2. Clicca **+** → **New repository**
3. Nome: `calendario-triveneto` (o quello che preferisci)
4. Metti **Public** ✓
5. Spunta **Add a README file** ✓
6. Clicca **Create repository**

### 2.2 Carica il file HTML
1. Nel repository appena creato, clicca **Add file** → **Upload files**
2. Trascina il file `calendario_donne_2026.html`
3. **IMPORTANTE**: rinominalo `index.html` prima di caricarlo
   (oppure dopo: clicca sul file → matita → cambia nome in `index.html`)
4. Clicca **Commit changes**

### 2.3 Attiva GitHub Pages
1. Nel repository, vai su **Settings** (in alto)
2. Nel menu laterale, clicca **Pages**
3. Sotto **Source**, seleziona **Deploy from a branch**
4. Branch: **main** / Folder: **/ (root)**
5. Clicca **Save**
6. Aspetta 1-2 minuti → apparirà il tuo URL:
   **`https://tuonome.github.io/calendario-triveneto/`**

---

## PARTE 3 — Prima apertura (tu come Admin)

1. Apri il tuo URL GitHub Pages
2. Vedrai la schermata di connessione
3. In basso clicca **"Clicca qui per configurare come admin"**
4. Inserisci:
   - **API Key**: la tua Secret Key da JSONBin
   - **Bin ID**: il tuo Bin ID
   - **Password Admin**: `triv2026admin`
     *(puoi cambiarla nel file HTML cercando `ADMIN_PASS_HASH`)*
   - **Nome**: es. "Admin" o il tuo nome
5. Clicca **Connetti come Admin**
6. Il calendario si apre con i dati già caricati ✓
7. Le tue credenziali vengono ricordate — non dovrai reinserirle

---

## PARTE 4 — Condividi con i tecnici

### Cosa inviare ai tecnici (copia e incolla):
```
Ciao! Ecco il calendario disponibilità gare 2026.

🔗 Link: https://tuonome.github.io/calendario-triveneto/

Per accedere:
- Bin ID:  6840abcd1234ef56789012
- API Key: $2b$10$xxxxxxxxxxxxxxxx

Apri il link, inserisci questi dati e il tuo nome.
Le tue disponibilità vengono salvate automaticamente.
```

### Come accede un tecnico:
1. Apre il link
2. Inserisce Bin ID, API Key e il suo nome
3. Clicca **Connetti e Apri**
4. Compila le disponibilità → si sincronizzano per tutti automaticamente

---

## RIASSUNTO RUOLI

| Chi | Cosa può fare |
|-----|--------------|
| **Admin** (tu) | Tutto: aggiungere/modificare/eliminare gare + disponibilità |
| **Tecnico** | Solo: inserire/modificare le proprie disponibilità |

---

## FAQ

**I dati vengono aggiornati automaticamente?**
Sì, ogni 30 secondi la pagina controlla se ci sono novità. Puoi anche cliccare ↺ Aggiorna.

**Cosa succede se due persone modificano insieme?**
L'ultima modifica vince (last-write-wins). Per le disponibilità non è un problema perché ognuno tocca solo le proprie.

**Posso cambiare la password admin?**
Sì: nel file HTML cerca `ADMIN_PASS_HASH` e cambia il valore tra virgolette. Poi ricarica il file su GitHub.

**Il Bin ID è "pubblico"?**
Sì, chiunque abbia API Key + Bin ID può leggere i dati. Per un calendario di squadra è accettabile. Se vuoi più sicurezza, JSONBin ha piani a pagamento con accesso privato.

**Quante persone possono usarlo?**
JSONBin gratuito ha 10.000 richieste al mese. Con aggiornamento ogni 30s = ~2.880/giorno per utente. Ottimale fino a 3-4 utenti attivi contemporaneamente.