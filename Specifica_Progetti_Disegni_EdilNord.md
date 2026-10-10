# Edil Nord – Modulo "Progetti e Disegni"

Documento di riferimento: raccoglie quanto deciso finora. Va letto prima di ogni sessione di sviluppo su questo modulo.

Ultimo aggiornamento: 10 ottobre 2026

---

## 1. Obiettivo

Aiutare i collaboratori a **disegnare i progetti dei clienti** e a tenere **in un unico posto** tutto quello che riguarda ogni cliente: disegni, foto di cantiere, file e note.

Il modulo **non è un programma separato**. Va **integrato nel software commissioni** che ho già creato (quello dove ci sono i clienti), **non** nell'app Ordini Magazzino. Vedi punto 7.

---

## 2. Come si lavora oggi

- Il cliente porta un **foglio con le misure**. I clienti più organizzati portano un **file CAD**.
- Il collaboratore **disegna a mano** su un foglio bianco, con il righello.
- I disegni riguardano **stanze singole**, non ambienti grandi:
  - **Bagni: circa 95%**. Sono il vero obiettivo del modulo.
  - **Cucine: circa 5%**. Hanno già un loro **software dedicato**, quindi NON vanno ridisegnate qui. Basta allegare al progetto il file o PDF esportato dal software cucine.
- Foto di cantiere e documenti sono sparsi: non c'è un archivio per cliente.

---

## 3. Scelte di fondo

1. **Niente programma CAD da zero.** Non serve e costerebbe troppo. Serve uno strumento semplice e specifico per i bagni.
2. **Niente seconda anagrafica clienti.** I clienti esistono già nel **software commissioni**. Il progetto si collega al cliente o alla commissione, senza ricopiare i dati.
3. **Procedere per fasi**, partendo da una versione minima fatta provare a un collaboratore.
4. **Prima definire, poi sviluppare.** Si ragiona in chat (consuma meno) e si passa allo sviluppo con richieste piccole e precise.

---

## 4. Le fasi

### Fase 1 – Archivio Cliente → Progetti → File
È la più semplice ed è subito utile.
- Ogni cliente o commissione ha **uno o più progetti** (es. "Bagno piano terra", "Bagno mansarda").
- In ogni progetto si possono caricare:
  - foto di cantiere, anche scattate dal telefono sul posto;
  - la foto del foglio misure portato dal cliente;
  - PDF, file CAD, il file del software cucine;
  - note libere;
  - "tutto quello che può servire": il progetto deve accettare qualsiasi tipo di allegato.
- Le foto caricate in cantiere si vedono subito in ufficio.

### Fase 2 – Editor disegno bagno
- Si inseriscono le **misure delle pareti** e la stanza si disegna da sola, in scala. Deve gestire anche stanze a L e con rientranze.
- Si posizionano **porte e finestre** sulle pareti.
- Si trascinano gli elementi da una **libreria con misure standard modificabili**: WC, bidet, lavabo, piatto doccia, vasca, termoarredo, mobile.
- **Quote automatiche.**
- **Stampa o PDF** da consegnare al cliente.
- Il disegno si salva nel progetto e si può riaprire e modificare.

### Fase 3 – Collegamento con gli ordini
- Dal progetto si crea l'ordine dei materiali, oppure si collegano al progetto gli ordini già fatti.
- In futuro, se serve: metri quadri di piastrelle calcolati dal disegno, elenco materiali, preventivo.

---

## 5. Permessi

Due livelli:
- **"Vede tutto"** (ufficio, titolare): tutti i clienti e tutti i progetti. Può assegnare i progetti ai collaboratori.
- **"Vede i suoi"**: solo i progetti a cui è assegnato. *(Da confermare: assegnati a lui o creati da lui? Vedi punto 8.)*

Importante: i permessi devono essere applicati **davvero sui dati**, non solo nascondendo i pulsanti. Foto, indirizzi e misure dei clienti sono dati riservati.

---

## 6. Collegamento con i clienti (software commissioni)

Poiché il modulo va **dentro** il software commissioni, i progetti si collegano **direttamente** ai clienti già presenti: nessuna importazione necessaria. (La tabella sotto resta solo come riferimento, se in futuro servisse collegare un altro programma.)

| Se il software commissioni è… | Soluzione |
|---|---|
| Fatto da me, sullo stesso sistema dati | Il modulo legge i clienti direttamente da lì (soluzione migliore) |
| Un gestionale che esporta in Excel/CSV | Si importa l'elenco ogni tanto con un pulsante "Aggiorna clienti" |
| Un gestionale chiuso, senza esportazione | Nel progetto si scrivono a mano il numero di commissione e il nome del cliente |

---

## 7. Software esistente

**Dove va integrato il modulo: nel SOFTWARE COMMISSIONI** (dove ci sono già i clienti). Link: *da aggiungere*.

Non va integrato nell'app Ordini Magazzino. Quella resta separata e, al massimo, in Fase 3 si collega ai progetti.

Altri miei software (artifact di Claude):

- **Ordini Magazzino** (app ordini, NON è dove va il modulo): https://claude.ai/artifact/3sLBPJnXhK2d3oda8AqQdJ
  - Catalogo prodotti con ricerca, preferiti e soprannomi.
  - Carrello con quantità, unità di misura, note e voci fuori catalogo.
  - Cliente scritto come **testo libero**, senza anagrafica.
  - Elenco ordini con stato "in attesa" / "evaso" e avviso sonoro.
  - Nome dell'operatore.
  - Dati nel **database condiviso dell'artifact**, con riconoscimento dell'utente.
Altri artifact collegati al lavoro:
- Database prezzi e fatture fornitori: https://claude.ai/artifact/1gujZbSs6spP8Jho3YE8et
- Preventivo Edil Nord – Redesign: https://claude.ai/artifact/MYKXpusy5no2q6EeQKALqK
- Progetti Edil Nord: https://claude.ai/artifact/LzLbbxYp3nsBZhwDTLsPyw. È una pagina **vetrina** del sito, con lavori fatti e foto. NON è il gestionale.

Nota tecnica: se il software commissioni è anche lui un artifact, il modulo può usare le stesse funzioni (database condiviso, riconoscimento utente, caricamento file e foto). Prima di iniziare vanno **verificati i limiti** di spazio per foto e file e il funzionamento dei permessi per utente.

Il repository GitHub `emanuelezanet/Edilnord-ordini` ("Buoni di Carico") **non c'entra** con questo modulo. Le osservazioni fatte su quel codice non valgono qui.

---

## 8. Domande ancora aperte

1. ~~Dove va integrato?~~ **Deciso: nel software commissioni.**
2. Link del **software commissioni**, e com'è fatto (artifact di Claude? dove salva i dati?)
3. "Vede i suoi" vuol dire progetti **assegnati** al collaboratore o progetti **creati** da lui?
4. I collaboratori lo useranno di più in **ufficio (PC)** o in **cantiere (tablet/telefono)**?
5. Quali elementi del bagno servono nella libreria, e con quali misure standard?

---

## 9. Prossimo passo

1. Rispondere alle domande del punto 8.
2. Scrivere la specifica dettagliata della **Fase 1**: campi del cliente e del progetto, tipi di file, chi vede cosa, schermate.
3. Sviluppare la Fase 1 con richieste piccole e precise e farla provare a un collaboratore.

### Consigli per non consumare troppo utilizzo
- Domande e ragionamenti in **chat**, sviluppo vero e proprio solo quando la specifica è chiara.
- Richieste **piccole e precise** ("aggiungi il campo X alla schermata Y"), non "migliora l'app".
- **Una sessione nuova per ogni compito**, invece di conversazioni lunghissime.
