# daphne-ontological-extraction
Dataset strutturato della cultura materiale ne "L'Isola del Giorno Prima" di Umberto Eco. Protocollo v1.1

# Progetto Daphne: Ontologia della Cultura Materiale

Questo repository ospita il dataset strutturato relativo al romanzo *L'Isola del Giorno Prima* di Umberto Eco.

## Struttura del Repository
Il repository è organizzato per versioni, in modo da tracciare l'evoluzione del metodo di estrazione in base ai feedback ricevuti.

## Note Metodologiche (v1.1)
L'attuale protocollo corregge i limiti di arbitrarietà della versione precedente introducendo:
- **Calibrazione Pesi:** Sistema a modificatori cumulativi (0.80 base + specificità tecnica/interazione motoria) per eliminare la soggettività del modello.
- **Atomizzazione dei Regimi:** Scomposizione obbligatoria delle entità in record distinti per distinguere Reale, Memoria e Finzione.
- **Ancoraggio Filologico:** Obbligo di citazione del marcatore temporale nel campo `contesto`.

## Struttura del Repository
- `METODOLOGIA_v1.1.md`: Il prompt di sistema utilizzato per l'estrazione.
- `DATA`: Estrazioni JSON validate.
