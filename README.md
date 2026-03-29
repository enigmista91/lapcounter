# Contagiri Atletica (garav2)

**Contagiri Atletica** è una semplice ma potente applicazione web a pagina singola sviluppata in HTML, CSS e JavaScript per la gestione e il tracciamento dei giri durante le gare di atletica leggera su pista. 

L'interfaccia intuitiva consente a giudici o allenatori di monitorare più atleti contemporaneamente, registrando passaggi, calcolando i giri mancanti e gestendo sia aggiornamenti individuali che di gruppo.

## ✨ Funzionalità Principali

- **Configurazione Gara**: 
  - Inserimento dei pettorali degli atleti partecipanti (separati da virgola).
  - Impostazione della distanza totale della gara.
  - Calcolo automatico del numero di giri/passaggi previsti.
- **Cronometro Integrato**: Display in tempo reale (`MM:SS.ms`) del tempo trascorso dall'inizio della gara.
- **Gestione Atleti (Individuale)**:
  - Ogni atleta ha una "scheda" dedicata cliccabile.
  - Ad ogni clic, il contatore dei giri decresce e viene registrato il tempo di passaggio.
  - Segnalazione automatica di **Campana** (ultimo giro) e **Arrivo** a fine gara.
- **Aggiornamento di Gruppo (Mass Update)**:
  - Un bottone dedicato permette di scalare contemporaneamente un giro a tutti gli atleti attivi. Perfetto per gestire gruppi compatti.
- **Log degli Eventi**: 
  - Registrazione cronologica sul display laterale/inferiore di ogni singolo passaggio, arrivo o aggiornamento collettivo, mantenendo trasparenza sull'evoluzione cronometrica.
- **Reset e Sicurezza**: Conferme prima dell'esecuzione di azioni ad alto impatto (es. Reset totale della gara o Mass Update) per prevenire clic accidentali.

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
> **Ottimizzazione Tablet/Mobile**: L'interfaccia con pulsanti ampi ("cards") è ottimizzata anche per l'utilizzo in pista tramite tablet o schermi touch.

## 🛠 Stack Tecnologico

- **UI/Struttura**: HTML5
- **Stilizzazione**: CSS in linea / StyleSheet interno (Colori flat pastello, modalità Responsive parziale, interazioni base).
- **Logica**: Vanilla JavaScript (Gestione intervalli timer, manipolazione DOM, elaborazione array atleti, stato dinamico a singola pagina).

## 📄 Licenza / Note

File originale di riferimento: `garav2.html`. 
La versione `v2` introduce aggiornamenti di quality-of-life come la comoda funzionalità di *Mass Upate* per alleggerire il carico al giudice al passaggio del gruppo compatto.
