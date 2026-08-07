# TiaAddIns-dist

Repository di distribuzione: contiene **solo i binari** degli strumenti TIA Portal
di CTF Automazioni. I sorgenti stanno in una repository privata separata.

Serve all'aggiornamento automatico: l'applicazione installata interroga le release
di questa repository e, se ne trova una più recente, la scarica e si riavvia.

## Contenuto delle release

| File | Cosa è |
|---|---|
| `CtfProDiag.App-<versione>.zip` | applicazione desktop, da usare sulla macchina dove gira TIA Portal |

Dalla 0.11.2 la release contiene **solo lo zip**. Il vecchio add-in
`CtfProDiag-V21.addin` non viene più pubblicato: serviva a lanciare
l'applicazione dal menu di TIA, ma dalla 0.10.0 l'applicazione trova da sola le
sessioni di TIA aperte e fa scegliere su quale lavorare. Chi ha già l'add-in
installato può tenerlo, continua a funzionare; nelle release precedenti il file
è ancora scaricabile.

## Installazione

Scarica lo zip ed estrailo in una cartella qualsiasi, dove vuoi. Avvia
`CtfProDiag.App.exe`.

L'applicazione è **portatile**: tutto quello che legge e scrive sta sotto la
cartella da cui viene lanciata.

```
CtfProDiag\
   CtfProDiag.App.exe   manuale.html   settings.json
   Standard\    i riferimenti da applicare ai progetti (.dat e .json)
   Progetti\    una cartella per progetto, con le fotografie prima e dopo
   Log\
```

Sposti la cartella dove vuoi e non perdi niente. Non serve installare altro: le
librerie Openness vengono trovate da sole nella TIA Portal già presente sulla
macchina.

Dalla 0.11.4 il contenuto di `Standard\` **non va procurato**: al primo avvio
l'applicazione ci scrive da sola i riferimenti dello standard CTF, e le pagine
funzionano subito. Se il tuo standard è diverso, sostituisci il file in
`Standard\` con il tuo: un riferimento che c'è già non viene mai toccato, né al
riavvio né agli aggiornamenti. Per tornare a quello di serie si cancella il file
e si riavvia.

Il manuale utente è dentro lo zip e si apre anche dal menu **? → Manuale utente**.

## Aggiornamento

All'avvio l'applicazione controlla le release di questa repository e, se ce n'è
una più recente, propone il passaggio. L'aggiornamento sovrascrive i file del
programma e **non tocca** le tue cartelle `Standard\`, `Progetti\` e `Log\`.

## Requisiti

- TIA Portal installato sulla stessa macchina dell'applicazione
- utente Windows appartenente al gruppo **Siemens TIA Openness**
- .NET Framework 4.8
