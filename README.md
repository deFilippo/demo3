# SPECIFICA REQUISITI SNA4SLACK

### INTRODUZIONE
1. - Glossario dei termini utilizzati
2. - Definizione requisiti utente
3. - Requisiti specifici di sistema:
		- _funzionali_ (RF)
		- _non funzionali_ (RNF)
4. - Validazione requisiti specifici

L'obiettivo del seguente documento è quello di definire in modo corretto e completo i requisiti che il software da produrre deve rispettare.

#### 1. - GLOSSARIO
| Termine | Descrizione | Dati	|
|    :--  |    --    	| --:   |
| Member  |  utente o membro iscritto ad un Channel| id_utente , nome , username , id_channel  , display_name |
| Channel| canale di utenti, usato per le conversazioni tra utenti su un dominio specifico |  id_channel , nome , creato_da , membri |
| help | aiuto sulla sintassi dei comandi da inserire per interrogare la base di dati |
|mention| tag tra utenti che permette di segnalare il messaggio al destinatario nel caso in cui l'utente che scrive usi la sintassi @utente_y| 	@display_name | 
|lista pesata	| indica la cardinalità o numero di messaggi da From a To, dove From è chi scrive , To è chi riceve | |

#### 2. - Definizione requisiti utente 

-User stories- ,  permettono di definire in linea generale le funzionalità che il sistema deve possedere.

1. - In qualità di utente voglio visualizzare la lista dei Member
2. - In qualità di utente voglio visualizzare la lista dei Channel
3. - In qualità di utente voglio visualizzare la lista dei Member raggruppati per Channel
4. - In qualità di utente voglio visualizzare la lista dei Member di un Channel
5. - In qualità di utente voglio poter avere informazioni di help
6. - In qualità di utente voglio visualizzare la lista dei @mention
7. - In qualità di utente voglio visualizzare la lista dei @mention che partono da uno User
8. - In qualità di utente voglio visualizzare la lista dei @mention che arrivano a uno user
9. - In qualità di utente voglio visualizzare la lista pesata dei @mention
10. - In qualità di utente voglio visualizzare la lista pesata dei @mention che partono da uno User
11. - In qualità di utente voglio visualizzare la lista pesata dei @mention che arrivano a uno User

##### 3. - Requisiti specifici di sistema
###### 3.1 - Funzionali
>RF1 -> Il sistema deve permettere la visualizzazione della lista dei Member  
	RF1.1 -> Un Member deve essere identificato in modo univoco. (id_utente)  
>RF2 -> Il sistema deve permettere la visualizzazione della lista dei Channel  
	RF2.1 -> Un Channel deve essere identificato in modo univoco. (id_channel)  
>RF3 -> Il sistema deve permettere la visualizzazione della lista completa dei Member raggruppati per Channel  
>RF4 -> Il sistema deve permettere la visualizzazione della lista dei Member di un Channel  
>RF5 -> Il sistema deve permettere la visualizzazione di informazioni di Help  
>RF6 -> Il sistema deve permettere la visualizzazione della lista dei @mention  
	RF6.1 -> Il sistema deve permettere la visualizzazione della lista dei @mention in un dato Channel  
>RF7 -> Il sistema deve permettere la visualizzazione della lista dei @mention che partono da un User  
	RF7.1 -> Il sistema deve permettere la visualizzazione della lista dei @mention che partono da un User in un dato Channel  
>RF8 -> Il sistema deve permettere la visualizzazione della lista dei @mention che arrivano ad un User  
	RF8.1 -> Il sistema deve permettere la visualizzazione della lista dei @mention che arrivano ad un User in un dato Channel  
>RF9 -> Il sistema deve permettere la visualizzazione della lista pesata dei @mention  
	RF9.1 ->  Il sistema deve permettere la visualizzazione della lista pesata dei @mention di un dato Channel  
>RF10 -> Il sistema deve permettere la visualizzazione della lista pesata dei @mention che partono da uno User   
	RF10.1 -> Il sistema deve permettere la visualizzazione della lista pesata dei @mention che partono da uno User in un dato Channel  
>RF11 -> Il sistema deve permettere la visualizzazione della lista pesata dei @mention che arrivano ad un User     
	RF11.1 -> Il sistema deve permettere la visualizzazione della lista pesata dei @mention che arrivano ad un User in un dato Channel  
>RF12 -> Il sistema mette a disposizione dell'utente specifici comandi  
	RF12.1 -> Se l'utente non rispetta i comandi il sistema genera messaggi d'errore  

###### 3.2 - Non Funzionali
>RNF1 -> Il sistema deve essere disponibile 24h/24.  
>RNF2 -> Il sistema deve rispondere ad un comando in tempi brevi soprattutto per estrazione di dati da piccoli database.  
>RNF3 -> Il sistema deve essere utilizzato da linea di comando.  
>RNF4 -> Il sistema deve essere indipendente dal sistema operativo utilizzato.  
>RNF5 -> Il sistema deve occupare una quantità limitata di memoria.  
>RNF6 -> Il sistema deve saper gestire casi di eventi eccezionali.  
>RNF7 -> Il sistema deve operare su file .json per estrarre le informazioni richieste dall'utente  


##### 4. - Validazione requisiti specifici
Eseguiti opportuni test per ogni requisito funzionale. Verifiche soddisfatte riportate di seguito:

  RF1
  Verificare che sia possibile fare la richiesta da linea di comando
  Verificare che l'output sia visualizzato su standard output
  Verificare che sia possibile specificare il workspace con il nome completo del file zippato, con il percorso assoluto o relativo
  Verificare che ci sia un file esportato associato al workspace
  Verificare che i Member siano visualizzati uno per riga
  Verificare che i Member del workspace siano tutti presenti
  Verificare che non siano visualizzati Member estranei al workspace

  RF2
  Verificare che sia possibile fare la richiesta da linea di comando
  Verificare che l'output sia visualizzato su standard output
  Verificare che sia possibile specificare il workspace con il nome completo del file zippato, con il percorso assoluto o relativo
  Verificare che ci sia un file esportato associato al workspace
  Verificare che i Channel siano visualizzati uno per riga
  Verificare che i Channel del workspace siano tutti presenti
  Verificare che non siano visualizzati Channel estranei al workspace

  RF3
  Verificare che sia possibile fare la richiesta da linea di comando
  Verificare che l'output sia visualizzato su standard output
  Verificare che sia possibile specificare il workspace con il nome completo del file zippato, con il percorso assoluto o relativo
  Verificare che ci sia un file esportato associato al workspace
  Verificare che i Member e Channel siano visualizzati uno per riga, con I Member visualizzati subito dopo il Channel a cui appartengono
  Verificare che sia possibile distinguere quale nome è un "Member" e quale è un Channel
  Verificare che i Channel siano tutti presenti
  Verificare che non siano visualizzati Channel estranei al workspace
  Verificare che i Member di un Channel siano tutti presenti
  Verificare che non siano visualizzati Member estranei al Channel

  RF4
  Verificare che sia possibile fare la richiesta da linea di comando
  Verificare che l'output sia visualizzato su standard output
  Verificare che sia possibile specificare il workspace con il nome completo del file zippato, con il percorso assoluto o relativo
  Verificare che ci sia un file esportato associato al workspace
  Verificare che sia possibile specificare il Channel
  Verificare che i Member siano visualizzati uno per riga dopo il Channel specificato
  Verificare che i Member del Channel specificato siano tutti presenti
  Verificare che non siano visualizzati Member estranei al Channel specificato
 
  RF5
  verificare che l'help possa essere richiesto digitando il nome del programma senza parametri aggiuntivi
  verificare che l'help sia suggerito se un comando digitato non è valido
  verificare l'help sia mostrato su standard output
  verificare che siano presenti i comandi per tutte le funzionalità

  RF6
  Verificare che per ogni @mention sia visualizzata una riga con la coppia (From, To) dove From è
	lo User che scrive il messaggio con il @mention e To è lo User menzionato.
  Verificare che le coppie (From, To) non siano ripetute
  Verificare che le coppie (From, To) corrispondenti a un @mention siano tutte presenti
  Verificare che siano visualizzate solo coppie (From, To) corrispondenti a un @mention
  Verificare che sia possibile specificare il Channel e, nel caso sia specificato, la lista sia ristretta ai soli @mention del Channel

  RF7
  Verificare che sia possibile specificare lo User da cui partono i @mention
  Verificare che per ogni @mention sia visualizzata una riga con la coppia (From, To) dove From è lo User specificato nel comando e To è lo User menzionato.
  Verificare che le coppie (From, To) non siano ripetute
  Verificare che le coppie (From, To) corrispondenti a un @mention siano tutte presenti
  Verificare che siano visualizzate solo coppie (From, To) corrispondenti a un @mention
  Verificare che sia possibile specificare il Channel e, nel caso sia specificato, la lista sia ristretta ai soli @mention del Channel

  RF8
  Verificare che sia possibile specificare lo User a cui arrivano i @mention
  Verificare che per ogni @mention sia visualizzata una riga con la coppia (From, To) dove è lo User
  che scrive il messaggio con il @mention e To è lo User menzionato e specificato nel comando.
  Verificare che le coppie (From, To) non siano ripetute
  Verificare che le coppie (From, To) corrispondenti a un @mention siano tutte presenti
  Verificare che siano visualizzate solo coppie (From, To) corrispondenti a un @mention
  Verificare che sia possibile specificare il Channel e, nel caso sia specificato, la lista sia ristretta ai soli @mention del Channel

  RF9
  Verificare che per ogni @mention sia visualizzata una riga con la tripla (From, To, Weight) dove From è lo User che scrive il messaggio con il @mention, To è lo User menzionato, e Weight è il peso associato che riporta il numero di mention da From a To:
  Verificare che le triple (From, To, Weight) non siano ripetute
  Verificare che le triple (From, To, Weight) corrispondenti a un @mention siano tutte presenti
  Verificare che siano visualizzate solo triple (From, To, Weight)* corrispondenti a un @mention
  Verificare che sia possibile specificare il Channel e, nel caso sia specificato, la lista sia ristretta ai soli @mention del Channel

  RF10
  Verificare che sia possibile specificare lo User da cui partono i @mention
  Verificare che per ogni @mention sia visualizzata una riga con la tripla (From, To, Weight) dove From è lo User specificato nel comando e To è lo User menzionato, e Weight il numero di mention.
  Verificare che le triple (From, To, Weight) non siano ripetute
  Verificare che le triple (From, To, Weight) corrispondenti a un @mention siano tutte presenti
  Verificare che siano visualizzate solo triple (From, To, Weight) corrispondenti a un @mention
  Verificare che sia possibile specificare il Channel e, nel caso sia specificato, la lista sia ristretta ai soli @mention del Channel

  RF11
  Verificare che sia possibile specificare lo User a cui arrivano i @mention
  Verificare che per ogni @mention sia visualizzata una riga con a tripla (From, To, Weight) dove From è lo User che scrive il messaggio con il @mention, To è lo User menzionato e specificato nel comando e Weight il numero di mention.
  Verificare che le triple (From, To, Weight) non siano ripetute
  Verificare che le triple (From, To, Weight) corrispondenti a un @mention siano tutte presenti
  Verificare che siano visualizzate solo triple (From, To, Weight) corrispondenti a un @mention
  Verificare che sia possibile specificare il Channel e, nel caso sia specificato, la lista sia ristretta ai soli @mention del Channel

