# daphne-ontological-extraction
Dataset strutturato della cultura materiale ne "L'Isola del Giorno Prima" di Umberto Eco. Protocollo v1.1

# Progetto Daphne: Ontologia della Cultura Materiale

Questo repository ospita il dataset strutturato relativo al romanzo *L'Isola del Giorno Prima* di Umberto Eco.

## Struttura del Repository
Il repository è organizzato per versioni, in modo da tracciare l'evoluzione del metodo di estrazione in base ai feedback ricevuti.

## Note Metodologiche (v1.1)

Il dataset è generato attraverso un'analisi ontologica del testo basata su quattro pilastri tecnici:

#### 1. Architettura e Densità
Il protocollo impone una granularità minima di **10 record per capitolo**. Ogni entità (oggetto, percezione o concetto) viene estratta come record autonomo nell'array `entita_marcate`, garantendo la profondità statistica del dataset.

#### 2. Tassonomia del Peso Materico (0.0 - 1.0)
Il valore `peso_materico` è determinato da un sistema a modificatori cumulativi che elimina l'assegnazione soggettiva:
* **Fascia Alta (0.70 - 1.0) | Lista Pratica:** Oggetti fisici sulla scena. Base 0.80 + modificatore terminologia tecnica (+0.10) + modificatore interazione motoria (+0.10).
* **Fascia Media (0.40 - 0.60) | Percezione Sensoriale:** Fenomeni ambientali (luci, suoni, odori) pesati in base all'intensità descrittiva (0.40 sfumato, 0.60 invasivo).
* **Fascia Bassa (0.10 - 0.30) | Lista Poetica:** Astrazioni, ricordi o metafore. Serve a garantire la separazione spaziale dagli elementi fisici.

#### 3. Protocollo di Atomizzazione
In presenza di sovrapposizione tra piani narrativi, il sistema scompone l'entità in record distinti classificati per **Regime**:
* **REALE:** Legato alla presenza fisica sulla nave.
* **MEMORIA:** Legato ad analessi e marcatori temporali passati.
* **FINZIONE:** Legato a immaginazione pura o proiezioni mentali.

#### 4. Ancoraggio Filologico
Ogni classificazione è validata nel campo `contesto`, che riporta la porzione minima di testo e il marcatore (verbo o avverbio) che determina il regime e il peso assegnato.


## Struttura del Repository
- `METODOLOGIA_v1.1.md`: Il prompt di sistema utilizzato per l'estrazione.
- `DATA`: Estrazioni JSON validate.
