# Java Network Remote Calculator (Verifica)

Progetto Java che implementa un servizio di calcolo distribuito tramite protocollo TCP/IP, permettendo l'elaborazione di operazioni aritmetiche su un server remoto.

## Descrizione
Il software permette a un Client di inviare espressioni matematiche semplici a un Server dedicato. Il sistema riceve la richiesta, analizza la stringa per identificare operandi e operatori, esegue il calcolo in tempo reale e restituisce il risultato al mittente, gestendo l'intero ciclo di vita della connessione Socket.



## Funzionamento del Sistema:
* **Connessione TCP**: Stabilimento di un canale di comunicazione affidabile tra Client e Server sulla porta 6789.
* **String Parsing**: Scomposizione della stringa ricevuta (es. "10 + 5") tramite tokenizzazione per isolare i valori numerici e il simbolo dell'operazione.
* **Elaborazione Remota**: Esecuzione della logica aritmetica (addizione, sottrazione, moltiplicazione, divisione) lato server per alleggerire il carico del client.
* **Gestione Risorse**: Chiusura automatica degli stream di input/output e della socket al termine di ogni singola operazione per ottimizzare l'uso della rete.
* **Server Iterativo**: Capacità del server di rimanere in ascolto continuo per servire nuove richieste sequenziali senza interruzioni.

## Tecnologie e Concetti
* **Java Network (java.net)**: Utilizzo delle classi `Socket` e `ServerSocket` per la comunicazione di rete.
* **I/O Streams**: Gestione dei flussi di dati tramite `BufferedReader` per la lettura e `DataOutputStream` per la scrittura rapida di byte.
* **Data Parsing**: Manipolazione avanzata di stringhe e conversione di tipi di dato (`Double.parseDouble`) per l'elaborazione numerica.
* **Protocollo Request-Response**: Implementazione di un modello di comunicazione sincrono tra i due endpoint.
