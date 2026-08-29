# Contagiri Atletica (garav2)

**Contagiri Atletica** è una semplice ma potente applicazione web a pagina singola sviluppata in HTML, CSS e JavaScript per la gestione e il tracciamento dei giri durante le gare di atletica leggera su pista.

L'interfaccia intuitiva consente a giudici o allenatori di monitorare più atleti contemporaneamente, registrando passaggi, calcolando i giri mancanti e gestendo sia aggiornamenti individuali che di gruppo.

## ✨ Funzionalità Principali

- **Configurazione Gara**:
  - Supporto per **Gare con Siepi** (Steeplechase), con gestione opzionale di Fossa Interna (390m di sviluppo pista) e Fossa Esterna (410m di sviluppo pista).
  - Inserimento dei pettorali degli atleti partecipanti (separati da virgola).
  - Validazione rigorosa numerica per l'inserimento dei pettorali.
  - Ordinamento automatico in ordine crescente dei pettorali in gara.
  - Controllo automatico anti-duplicati durante l'inserimento dei pettorali.
  - Impostazione della distanza totale della gara.
  - Scelta della lunghezza della pista (es. 400m o 200m).
  - Supporto per gare con siepi (2000m e 3000m) con calcolo dei passaggi differenziato per Riviera Interna o Esterna.
  - Calcolo automatico del numero di giri/passaggi previsti.
  - Inserimento opzionale di Data Gara, Ora e Nome del Meeting per una migliore archiviazione.
  - Guida all'uso integrata per assistere nella configurazione e nell'utilizzo.
- **Cronometro Integrato**: Display in tempo reale (`MM:SS.ms`) del tempo trascorso dall'inizio della gara.
- **Gestione Atleti (Individuale)**:
  - Visualizzazione in tempo reale della distanza percorsa all'interno della scheda dell'atleta.
  - Ogni atleta ha una "scheda" dedicata cliccabile.
  - Ad ogni clic, il contatore dei giri decresce e viene registrato il tempo di passaggio.
  - Segnalazione visiva di **Preavviso Campana** (animazione arancione lampeggiante a 2 giri dalla fine) e automatica di **Campana** (scheda rossa e **Avviso sonoro tramite Web Audio API** all'ultimo giro) e **Arrivo** a fine gara.
  - Visualizzazione in tempo reale della **Distanza Coperta** calcolata dinamicamente in base ai giri effettuati e alla lunghezza della pista.
  - Funzionalità di ritiro atleta in caso di abbandono della gara.
- **Aggiornamento di Gruppo (Mass Update)**:
  - Un bottone dedicato permette di scalare contemporaneamente un giro a tutti gli atleti attivi. Perfetto per gestire gruppi compatti.
- **Log degli Eventi**:
  - Registrazione cronologica sul display laterale/inferiore di ogni singolo passaggio, arrivo o aggiornamento collettivo, mantenendo trasparenza sull'evoluzione cronometrica.
- **Classifica in Tempo Reale e Finale**:
  - Modalità "Mostra Classifica" attivabile con apposito bottone a gara in corso o a gara conclusa.
  - Ordinamento dinamico per atleti completati, numero di giri e tempo.
  - Calcolo del distacco per atleti nello stesso giro e stato (DNS se 0 giri).
- **Dettaglio Giri**: Visualizzazione dinamica dei tempi totali e parziali di ogni singolo giro per tutti gli atleti, sia a gara in corso che a posteriori tramite l'archivio.
- **Condivisione e Stampa**:
  - Generazione di un **QR Code** con i risultati della gara, facilmente scansionabile per condividere la classifica al volo.
  - Condivisione istantanea della classifica della gara in corso (o archiviata) via **WhatsApp** ed **Email**.
  - Funzione **Stampa Classifica** per generare un foglio pulito ed essenziale, ottimizzato per la stampa, con la classifica finale o parziale.
- **Salvataggio di Sicurezza (Local Storage)**:
  - Lo stato della gara in corso viene salvato in tempo reale.
  - In caso di chiusura accidentale o ricarica della pagina, l'app proporrà il ripristino istantaneo della gara interrotta, evitando la perdita di dati preziosi.
- **Archivio Gare e Storico**:
  - Le gare completate o interrotte vengono archiviate automaticamente.
  - Sezione dedicata per consultare lo storico delle corse passate.
  - Possibilità di visualizzare e recuperare a posteriori la **Classifica Finale** e il **Dettaglio Passaggi** (tempi sul giro) per ogni gara ed atleta archiviato.
  - Gestione dell'archivio (eliminazione singola gara o svuotamento totale).
- **Reset e Sicurezza**:
  - Conferme prima dell'esecuzione di azioni ad alto impatto (es. Reset totale della gara o Mass Update) per prevenire clic accidentali.
  - Prevenzione delle vulnerabilità XSS per un inserimento e una visualizzazione sicura dei dati.

## 🚀 Utilizzo

Essendo un'applicazione client-side (senza backend dedicato), l'utilizzo è immediato:

1. **Avvio**: Scarica il file `garav2.html` (e i file a supporto, qualora fossero presenti) e aprilo in un qualsiasi browser moderno (Chrome, Firefox, Safari, Edge).
2. **Setup Iniziale**:
   - Inserisci la lista dei pettorali nella barra di testo iniziale (es: `1,2,5,10,23`).
   - Seleziona/inserisci la distanza desiderata.
   - Conferma la configurazione, passando alla dashboard di gara.
3. **Avvio Gara**: Clicca su **START** per attivare il cronometro e sbloccare le schede degli atleti.
4. **Pressione Schede**: Durante la gara, un clic sulla "card" dell'atleta o sul tasto del gruppo gestirà la detrazione del giro e aggiornerà il database di log con lo stampaggio del tempo corrente.
5. **Fine**: A completamento giri, la card indicherà l'arrivo al traguardo ("Arrivo").

> [!TIP]
> **Ottimizzazione Tablet/Mobile**: L'interfaccia con pulsanti ampi ("cards") è ottimizzata anche per l'utilizzo in pista tramite tablet o schermi touch. Inoltre, è presente il pulsante "Visuale mobile" per riorganizzare l'interfaccia ottimizzandola per gli schermi più piccoli.

## 🛠 Stack Tecnologico

- **UI/Struttura**: HTML5
- **Stilizzazione**: CSS in linea / StyleSheet interno (Colori flat pastello, modalità Responsive parziale, interazioni base).
- **Logica**: Vanilla JavaScript (Ottimizzazione ad alte prestazioni del timer tramite `requestAnimationFrame`, manipolazione DOM, elaborazione array atleti, stato dinamico a singola pagina, generazione suoni tramite Web Audio API).
- **Deploy Automatico**: Integrazione con GitHub Actions per il deploy FTP automatico a ogni aggiornamento del branch principale.

## 📄 Licenza / Note

File originale di riferimento: `garav2.html`.
Inoltre, il footer dell'applicazione include un collegamento diretto a questo repository GitHub per facilitare l'accesso al codice sorgente e la segnalazione di problemi.
La versione `v2` introduce aggiornamenti di quality-of-life come la comoda funzionalità di _Mass Upate_ per alleggerire il carico al giudice al passaggio del gruppo compatto.

Questo progetto è distribuito sotto licenza **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)**.

[![CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

In sintesi, sei libero di condividere e modificare questo materiale, a condizione che:

1. **Attribuzione**: Riconosci il credito adeguato all'autore originale.
2. **Non Commerciale**: Non utilizzi il materiale per scopi commerciali o per trarne profitto.
3. **Condividi allo Stesso Modo**: Se modifichi il materiale, devi distribuire i tuoi contributi con la stessa licenza dell'originale.

Per maggiori dettagli, consulta il file `LICENSE` incluso in questo repository o visita il [sito ufficiale Creative Commons](https://creativecommons.org/licenses/by-nc-sa/4.0/).

## 🤝 Contributi

Le Pull Request sono benvenute, tuttavia si prega di notare che **tutte le PR verranno mergiate esclusivamente dall'owner del progetto** dopo un'attenta revisione.
