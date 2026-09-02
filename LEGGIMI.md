# Il riparo di Sensi

La copia dell'archivio di *Dory's diary*. Non è codice: è quello che il codice
custodisce. Ogni commit è l'archivio com'era in quel momento.

## Cosa c'è dentro

- `db/` — gli archivi SQLite. Servono per rimettere tutto a posto e ripartire.
- `leggibile/` — gli stessi dati in JSON, da aprire senza l'app.
- `media/` — le fotografie.
- `archivio-aperto.json` — quale archivio era aperto.

## Come si torna indietro

Fermare l'app, poi copiare i file di `db/` dentro `dati/` del progetto:

    cp db/*.db ~/percorso/del/progetto/dati/

I file `.db-wal` e `.db-shm` che fossero rimasti lì vanno tolti prima: sono
la coda di scritture del database vecchio, e riferita a un file diverso non
vuol dire niente.

Per tornare a com'era una certa sera, `git log` per trovare il commit e
`git checkout <commit> -- db/` per riportare indietro solo gli archivi.
