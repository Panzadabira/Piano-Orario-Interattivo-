<p align="left">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS">
  <img src="https://img.shields.io/badge/Firebase_Firestore-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase">
  <img src="https://img.shields.io/badge/Architecture-Single_Page_App-8A2BE2?style=for-the-badge" alt="SPA">
</p>

# Gestore Piano Orario RS
> *Un pianificatore temporale interattivo e flessibile con architettura di sincronizzazione ibrida (Cloud Firestore + Fallback Locale JSON) e interfaccia Drag-and-Drop.*

---

## Panoramica del Progetto

Il **Gestore Piano Orario RS** è un'applicazione web autonoma (Single-Page Application) pensata per la gestione visuale di flussi di lavoro, orari e compiti complessi.

A differenza dei classici fogli di calcolo statichi, questo strumento unisce l'immediata ergonomia di una **bacheca Kanban interattiva** alla potenza di una **griglia temporale multidimensionale**. È progettato per garantire continuità operativa totale grazie a un sistema di salvataggio intelligente che connette in tempo reale i dati sul Cloud, ma è in grado di funzionare perfettamente anche offline tramite l'importazione e l'esportazione di file JSON.

---

## Funzionalità Principali

* 🖱️ **Drag-and-Drop Fluido & Naturale:** Sposta liberamente i task tra le diverse fasce orarie e categorie o rimettili temporaneamente in pausa nella bacheca di Backlog integrata.
* ☁️ **Sincronizzazione Cloud in Tempo Reale:** Connessione nativa a **Firebase Firestore**. Ogni modifica alla griglia, spostamento di un task o creazione di una colonna viene salvata istantaneamente nel cloud con un indicatore di stato di connessione visivo (*Ping telematico*).
* 🛡️ **Architettura di Fallback Resiliente:** Se la connessione al cloud non è disponibile, il sistema tenta automaticamente di caricare lo stato locale tramite il file `piano_orario.json`, garantendo zero tempi di inattività.
* 📊 **Griglia Altamente Dinamica:**
  * **Aggianta & Modifica Colonne:** Crea nuove fasce orarie (es. *RS 4*, *RS 8*), modificale o riordinale trascinandole visivamente.
  * **Gestione Righe per Categoria:** Suddividi il piano per aree tematiche colorate (es. *Personale*, *Istruzione*, *Logistica*, *Condotta*, *Urgenza*).
* 💾 **Backup & Portabilità (Export / Import JSON):** Esporta l'intera struttura (task, posizioni, righe e colonne) in un file `.json` portatile con un solo clic o importa un piano di backup per ripristinare uno stato precedente.
* 🎨 **UI / UX Moderna:** Costruito con **Tailwind CSS**, dotato di colonne bloccate per lo scorrimento orizzontale (*Sticky Header/Column*) e codice colore semantico per identificare visivamente le priorità.

---

## Stack Tecnologico & Architettura

L'intero sistema è ingegnerizzato all'interno di un unico file altamente ottimizzato che non richiede complessi processi di build o server locali di backend:

| Componente | Tecnologia Utilizzata |
| :--- | :--- |
| **Struttura & Core Logic** | HTML5 / Vanilla JavaScript (ES6+ Modules) |
| **Styling & Design System** | Tailwind CSS (tramite CDN ad alte prestazioni) & Inter Font |
| **Database & Auth** | Google Firebase (Firestore Database + Anonymous Authentication) |
| **Interattività** | Native HTML5 Drag and Drop API |

---

## Guida all'Avvio Rapido

Poiché il tool è una Single-Page Application basata su moduli ES6, l'installazione richiede zero passaggi. 

1. **Clona o Scarica il Repository:**
   ```bash
   git clone [https://github.com/Panzadabira/NOME-REPO-QUI.git](https://github.com/Panzadabira/NOME-REPO-QUI.git)
   cd NOME-REPO-QUI
Esecuzione Locale:
Per motivi di sicurezza legati ai moduli CORS di JavaScript (type="module"), apri il file HTML tramite un semplice server locale.

Se usi VS Code: Installa ed avvia l'estensione Live Server.
Se usi Python: Esegui da terminale:

Bash
python -m http.server 8000
Quindi apri il browser su http://localhost:8000.

```

 Guida all'Uso
1. Gestione dei Task
Creazione: Clicca sul pulsante blu + Nuovo Task. Assegna un titolo, un sottotitolo opzionale (es. il giorno o il blocco di riferimento) e una categoria di colore.

Modifica ed Eliminazione: Passa il mouse su un qualsiasi task presente nella griglia o nel Backlog; clicca sull'icona della matita in alto a destra per modificarne il contenuto o eliminarlo definitivamente.

2. Personalizzazione della Griglia
Usando i pulsanti + Colonna e + Riga puoi espandere la matrice temporale posizionando il nuovo elemento esattamente dove desideri (es. "Prima di: RS 13" o "Alla fine").

3. Bacheca Backlog
L'area grigia inferiore (Task non assegnati) funziona come una zona di parcheggio. Puoi trascinarvi i compiti temporaneamente sospesi o in attesa di essere programmati in una fascia oraria definitiva.

 Sicurezza & Persistenza dei Dati
Il piano utilizza una strategia di persistenza multi-livello:

Live Cloud State: I dati vengono iniettati in tempo reale su un percorso Firestore sicuro e isolato: artifacts/{appId}/public/data/planner_state/main.

Offline Data Portability: Puoi scaricare un'istantanea del database in qualsiasi momento cliccando su Esporta. Il file generato conterrà l'esatta mappatura delle coordinate della matrice (rowIndex, colIndex) per ogni task.
