
**Tris Multiplayer - Bangoni, Falchi, Ticciati**

Tris multiplayer con architettura client-server sviluppato in Java.


Come Avviare l'Applicazione

Opzione 1: Utilizzare le Classi Già Compilate

Se nella cartella `target/classes` sono presenti i file `.class` già compilati:

**1. Avviare il Server**

Aprire un terminale nella directory principale del progetto ed eseguire:

```bash
java -cp target/classes it.edu.marconi.pontedera.onmicrosft.Server
```

Il server si avvierà sulla porta 1234 e mostrerà:

Server avviato sulla porta 1234


**2. Avviare il Primo Client (Giocatore X)**

Aprire un secondo terminale ed eseguire:

```bash
java -cp target/classes it.edu.marconi.pontedera.onmicrosft.Client
```

Il client si connetterà e attenderà il secondo giocatore.

**3. Avviare il Secondo Client (Giocatore O)**

Aprire un **terzo terminale** ed eseguire:

```bash
java -cp target/classes it.edu.marconi.pontedera.onmicrosft.Client2
```

Una volta connessi entrambi i giocatori, la partita inizierà automaticamente!





**Come Giocare**

Regole del Gioco

- Il gioco si svolge su una griglia 3x3
- Il Giocatore X inizia per primo
- I giocatori si alternano inserendo il proprio simbolo (X o O) in una cella vuota
- Vince chi riesce a posizionare tre dei propri simboli in linea (orizzontale, verticale o diagonale)
- Se tutte le celle sono occupate senza vincitori, la partita termina in pareggio

Interfaccia di Gioco

Quando è il tuo turno, il client mostrerà:

```
TUO_TURNO
Riga (0-2): 
```

Inserisci un numero da 0 a 2 per la riga, premi Invio, poi inserisci un numero da 0 a 2 per la colonna.

Esempio:
```
Riga (0-2): 1
Colonna (0-2): 1
```

Questa mossa posizionerà il tuo simbolo nella cella centrale.


Visualizzazione della Griglia

Dopo ogni mossa, entrambi i giocatori vedranno la griglia aggiornata:

```
 X |   |  
-----------
   | O |  
-----------
   |   | X
```

Le celle vuote sono rappresentate da spazi.


Fine della Partita

La partita termina quando:
- Un giocatore vince (riceverà il messaggio "VITTORIA")
- L'altro giocatore perde (riceverà il messaggio "SCONFITTA")
- Tutte le celle sono piene senza vincitori (entrambi ricevono "PAREGGIO")
