# Turni Farmacia

App per gestire i turni settimanali della farmacia, da telefono e da PC.

- **Settimana**: turni giorno per giorno, con ore totali per persona confrontate con il contratto. Tocca un giorno per modificarlo (anche aprire la domenica o un festivo).
- **Orario base**: lo schema che si ripete ogni settimana; le modifiche ai singoli giorni hanno la precedenza.
- **Impostazioni**: personale, fasce rapide (Mattina 8:30–14:30, Pomeriggio 13:30–19:30…), collegamento ai dati.

L'app è una pagina statica pubblicata con GitHub Pages da questo repository (pubblico, contiene solo codice).
I dati stanno nel repository **privato** `farmasched-dati`: ogni salvataggio diventa un commit, quindi c'è lo storico completo.

## Messa online (una volta sola)

1. Carica in questo repository (`sbarbaorama/farmasched`) i file:
   `index.html`, `sw.js`, `manifest.webmanifest`, `icon.svg`, `icon-192.png`, `icon-512.png`, `README.md`.
   Dal sito: **Add file → Upload files**, trascina i file, poi **Commit changes**.
2. **Settings → Pages** → *Build and deployment* → Source: **Deploy from a branch** → Branch: **main**, cartella **/ (root)** → **Save**.
3. Dopo un minuto o due l'app è su **https://sbarbaorama.github.io/farmasched/**

## Token di accesso ai dati (uno, da usare su tutti i tuoi dispositivi)

1. GitHub → foto profilo → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Nome: es. `farmasched`. Scadenza: a scelta (quando scade, l'app ti chiede di inserirne uno nuovo).
3. **Repository access** → *Only select repositories* → `farmasched-dati`.
4. **Permissions → Repository permissions → Contents** → *Read and write*.
5. **Generate token**, copialo (si vede una sola volta) e incollalo nell'app alla prima apertura.

Il token resta salvato solo nel browser del dispositivo. Non metterlo mai in un file di questo repository.
Se perdi il telefono: revoca il token da GitHub e creane uno nuovo.

## Installare sul telefono

- **iPhone (Safari)**: apri l'indirizzo → Condividi → *Aggiungi alla schermata Home*.
- **Android (Chrome)**: apri l'indirizzo → menu ⋮ → *Installa app* / *Aggiungi a schermata Home*.

## Come sono salvati i dati

Nel repository `farmasched-dati`:

- `config.json` — personale, orario base, fasce rapide, chiusura nei festivi.
- `giorni/2026.json` — solo i giorni modificati rispetto all'orario base, per data (`"2026-10-12": {...}`).

Per tornare a una versione precedente: apri il file su GitHub → *History*.
