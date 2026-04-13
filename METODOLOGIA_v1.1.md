PROMPT DI ESTRAZIONE E ANALISI ONTOLOGICA - v1.1
Agisci come un Data Engineer specializzato in Digital Humanities. Il tuo compito è la trasformazione del testo del romanzo "L'Isola del Giorno Prima" in un dataset strutturato per l'analisi della cultura materiale e della stratificazione narrativa.

1. ARCHITETTURA DEL DATASET
Gerarchia Root: L'intero output deve essere incapsulato in un oggetto radice denominato "capitolo".

Granularità: Ogni entità estratta deve costituire un record autonomo all'interno di un array denominato "entita_marcate".

ID Univoci: Assegna a ogni record un ID alfanumerico progressivo (es: C1_OBJ_001).

Vincolo Quantitativo: Estrai almeno 10 entità significative dal testo fornito per garantire la profondità del dataset.

2. TASSONOMIA DEL PESO MATERICO (Scala di Densità Ontologica)
Assegna il valore peso_materico [float 0.0 - 1.0] seguendo rigorosamente questi criteri di calibrazione:

A. Fascia Alta (0.70 - 1.0) | Lista Pratica (Presenza Fisica)

Base 0.80: Oggetto solido presente sulla scena.

Modificatore Specificità (+0.10): Se l'entità è definita con terminologia tecnica o materica (es. "ottone", "ebano", "sartiame").

Modificatore Interazione (+0.10): Se l'oggetto è il fulcro di un'azione motoria diretta del protagonista (es. "impugnare", "percuotere").

Nota: Il valore massimo è 1.0.

B. Fascia Media (0.40 - 0.60) | Percezione Sensoriale

0.40 (Sfondo): Percezioni ambientali vaghe o diffuse (es. "luce del giorno", "odore di mare").

0.50 (Definita): Fenomeno sensoriale isolato e identificato (es. "un rintocco", "un profumo di rosa").

0.60 (Intensa): Percezioni invasive o descritte con aggettivi di intensità (es. "bagliore accecante", "odore nauseabondo").

C. Fascia Bassa (0.10 - 0.30) | Lista Poetica (Astrazione)

0.30 (Analessi): Ricordi nitidi di oggetti o luoghi un tempo reali nel passato (es. "i marmi di Casale").

0.20 (Simulacro): Visioni, sogni, proiezioni mentali o allucinazioni (entità non esistenti fisicamente).

0.10 (Metafora): Astrazioni pure, figure retoriche o concetti linguistici (es. "l'ancora della speranza").

3. PROTOCOLLO DI RISOLUZIONE AMBIGUITÀ
Atomizzazione: In presenza di una frase che mescola piani diversi (es. un oggetto reale paragonato a uno ricordato), genera due record distinti.

Identificazione Regime:

REALE: Legato alla permanenza sulla nave (verbi al presente/imperfetto).

MEMORIA: Legato al passato del personaggio (passato remoto, marcatori come "un tempo").

FINZIONE: Legato all'immaginazione pura o alla figura di Ferrante.

Ancoraggio Filologico: Il campo contesto deve isolare la porzione minima di testo che giustifica la classificazione. Se il regime è "memoria", il contesto deve includere il marcatore temporale o il verbo che lo determina.

4. VINCOLI TECNICI DI OUTPUT
Campi Obbligatori: id, oggetto, regime, peso_materico, contesto, pagina (sempre null).

Integrità: Genera ESCLUSIVAMENTE codice JSON valido. Nessun preambolo, introduzione o commento extra.
