# Informativa sulla privacy — Morosità Runner

Ultimo aggiornamento: 19 settembre 2026

Morosità Runner è un'estensione per Google Chrome che compila in automatico i form di verifica
inadempienza (art. 48-bis DPR 602/1973) sul portale MorosiWeb, riga per riga, a partire da un file CSV
scelto dall'utente.

## In sintesi

- **Nessun dato viene inviato allo sviluppatore né a terzi.** L'estensione non ha server propri,
  non usa analitica, non usa pubblicità, non usa sistemi di tracciamento.
- I dati del file CSV (ad esempio codici fiscali e importi) sono elaborati **solo sul tuo dispositivo**
  e sono inseriti unicamente nel portale che tu stesso hai aperto nella scheda attiva.
- Nessun dato è venduto, ceduto o usato per scopi diversi dalla funzione descritta sopra.

## Quali dati tratta l'estensione

| Dato | Dove resta | Perché |
|---|---|---|
| Righe del file CSV scelto dall'utente | Solo nella memoria temporanea del browser (`storage.session`), cancellata alla chiusura del browser o a fine elaborazione | Per compilare il form riga per riga e riprendere dopo una pausa |
| Esiti delle verifiche (es. "non inadempiente") | Solo nel pannello dell'estensione e nel file CSV che l'utente scarica volontariamente | Per mostrare l'avanzamento e produrre il rapporto finale |
| Impostazioni (ultima ricetta scelta, URL delle ricette, informazioni sull'ultimo aggiornamento) | Nell'archivio locale del browser (`storage.local`) | Per ricordare le preferenze |

Questi dati non lasciano il dispositivo, ad eccezione di quanto l'utente inserisce nel portale
attraverso la normale compilazione del form: in quel caso il destinatario è il gestore del portale,
con le sue regole, e la ricerca è compiuta dall'utente stesso tramite l'estensione.

## Comunicazioni di rete dell'estensione

L'unica connessione che l'estensione avvia per proprio conto è verso `raw.githubusercontent.com`,
per scaricare periodicamente (ogni 30 minuti circa) i file JSON delle **ricette**, cioè i nomi dei campi
del portale e la sequenza dei passi. In queste richieste **non viene inviato alcun dato dell'utente né
del file CSV**. Come per qualunque richiesta web, GitHub può registrare tecnicamente l'indirizzo IP, secondo
la propria informativa (<https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement>).

Le ricette sono solo dati: non contengono né eseguono codice. Ogni ricetta è verificata con hash SHA-256
e firma digitale prima dell'uso, e può richiedere soltanto un elenco chiuso di azioni (compilare un campo,
cliccare un elemento, attendere).

## Permessi richiesti

| Permesso | Uso |
|---|---|
| `storage` | Salvare le impostazioni e lo stato temporaneo dell'elaborazione |
| `scripting` | Compilare i campi e premere i pulsanti del form nella scheda del portale |
| `sidePanel` | Mostrare l'interfaccia dell'estensione |
| `alarms` | Controllare periodicamente se sono disponibili ricette aggiornate |
| `notifications` | Avvisare quando l'elaborazione si ferma (inadempiente, errore, fine) |
| `tabs` | Verificare che la scheda attiva sia il portale atteso |
| Accesso a `raw.githubusercontent.com` | Scaricare le ricette aggiornate |
| Accesso al sito del portale (richiesto solo all'avvio) | Compilare il form |

## Conformità alle norme di Chrome Web Store

L'uso dei dati è limitato alla funzione unica descritta sopra e rispetta la Chrome Web Store User Data
Policy, compresi i requisiti di "Limited Use". Nessun dato viene trasferito o venduto a terzi, né usato
per determinare l'affidabilità creditizia o per finalità di prestito.

## Conservazione e cancellazione

I dati temporanei sono eliminati alla chiusura del browser o al termine dell'elaborazione. Le impostazioni
sono rimosse disinstallando l'estensione. I file CSV scaricati dall'utente sono sotto il suo esclusivo controllo.

## Modifiche a questa informativa

Eventuali modifiche saranno pubblicate su questa pagina con una nuova data di aggiornamento.

## Contatti

Per domande sulla privacy apri una segnalazione (issue) su
<https://github.com/baleight/morosita-ricette/issues>.
