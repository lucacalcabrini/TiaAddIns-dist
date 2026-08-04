# TiaAddIns-dist

Repository di distribuzione: contiene **solo i binari** degli strumenti TIA Portal
di CTF Automazioni. I sorgenti stanno in una repository privata separata.

Serve all'aggiornamento automatico: l'applicazione installata interroga le release
di questa repository e, se ne trova una più recente, la scarica e si riavvia.

## Contenuto delle release

| File | Cosa è |
|---|---|
| `CtfProDiag.App-<versione>.zip` | applicazione desktop, da installare sulla macchina dove gira TIA Portal |
| `CtfProDiag-V21.addin` | add-in TIA Portal, da copiare in `Portal V21\AddIns\` con TIA chiuso |

## Installazione

L'applicazione si scompatta in una cartella qualsiasi e si avvia. Al primo avvio
crea le proprie impostazioni in `%APPDATA%\CtfProDiag\settings.json`, dove si
configurano cartella dei log, cartella delle configurazioni e versione di TIA.

L'add-in va installato una volta sola e non richiede aggiornamenti frequenti:
serve solo a richiamare l'applicazione dal menu contestuale di TIA Portal.

## Requisiti

- TIA Portal installato sulla stessa macchina dell'applicazione
- utente Windows appartenente al gruppo **Siemens TIA Openness**
- .NET Framework 4.8
