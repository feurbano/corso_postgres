# MATERIALE CORSO "Introduzione a PostgreSQL" 
--------
##### DOCENTI: *Ferdinando Urbano, Lorenzo de Ambrosis*
##### DATA: *24-25-26 Maggio 2016*
##### PRESSO: *HP TRAINING CENTER* 

<br>
<br>

## INTRODUZIONE AL CORSO (09:00-9:30; 24 Maggio)


### Presentazione dei docenti
### Presentazione partecipanti 
* Conoscenze pregresse, obiettivi di apprendimento

### Programma
* Percorso didattico (descrizione programma)
* Obiettivi formativi
* Organizzazione delle lezioni (orari, pause) 

<br>

## MODULO 1 (09:30-10:00; 24 Maggio): Introduzione a PostgreSQL

### Cos'è PostgreSQL
* PostgreSQL è un sistema avanzato di gestione di basi di dati (Database Management System, DBMS)
* Database: collezione di dati strutturati
* DBMS: insieme di componenti software per la creazione e la manipolazione di un database
* PostgreSQL è un Object Relational DataBase Management System:
 * Database relazionale
 * Supporta un modello di database object oriented (implementa oggetti, classi e ereditarietà)
 * L'estensione del modello di dati con tipi di dati e metodi personalizzati
* Open Source

### Cos'è un database relazionale
Il modello relazionale è un modello logico di rappresentazione o strutturazione dei dati di un database. L'assunto fondamentale del modello relazionale è che tutti i dati sono rappresentati come relazioni (tabelle) e manipolati con gli operatori dell'algebra relazionale. La tabella è un insieme multiplo di righe e di colonne. Rappresenta la relazione tra gli oggetti del mondo reale e le loro proprietà. Il modello relazionale consente al progettista di database di creare una rappresentazione consistente e logica dell'informazione. Il modello relazionale risponde al requisito dell'indipendenza dei dati e prevede una distinzione tra il livello fisico e il livello logico: questa capacità di astrazione ha fatto la sua fortuna nel mondo della gestione dati.
La struttura base del modello relazionale è composta da:

* Uno o più attributi o campi dato
* Un tipo di dato ed un dominio su quel tipo, definito come l'insieme dei valori che può assumere un determinato attributo o campo dato
* Un valore per ciascun attributo all'interno del dominio o tipo di dato consentito
* Una tupla cioè l'insieme non ordinato di valori assunti dagli attributi

Una volta creato e strutturato un database, è possibile estrarre le informazioni desiderate tramite una semplice interrogazione, chiamata anche query, basata su un semplice linguaggio (SQL).

### Perchè è importante usare i database
* Integrità 
  * Si prevengono errori di inserimento 
  * Si hanno solo informazioni "pulite"
  * Si formalizza l'informazione
* Sicurezza
  * I dati non vengono corrotti per errori degli operatori
  * I dati non possono essere usati da persone non autorizzate
* Riutilizzo dei dati
  * Uso dei dati per diverse applicazioni
  * Uso dei dati sul lungo termine
  * Integrazione dei dati con altri data sets
* Dati non vengono replicati
  * Uso di vari software client a seconda delle esigenze
  * Non ci sono versioni discordanti
* Condivisione dei dati
  * Dati possono essere usati da più persone contemporaneamente
  * Dati possono essere usati da dovunque
* Possibilità di gestire grandi moli di dati
  * Largo storage
  * Performance nell'uso dei dati
  * Strumenti analitici specifici (data mining)
* Punti di forza di PostgreSQL
  * Costo di licenza nullo
  * Assenza di vendor lock-in
  * Assenza di restrizioni sull'utilizzo
  * Interoperabilità
  * Funzionalità native mature e stabili
  * Multi-piattaforma
  * Stabilità
  * Sicurezza
  * Documentazione in tutte le sue forme
  * Supporto della comunità 
  * Supporto professionale
  * Estensioni molto potenti
  * Possibilità di usare molti linguaggi procedurali
  * Rapido sviluppo

### Alcune caratteristiche rilevanti
* Struttura server/client
* Connessioni remote
* Gestione concorrenza di utenti
* ACID. Perché le transazioni operino in modo corretto sui dati è necessario che i meccanismi che le implementano soddisfino quattro proprietà:
  * Atomicità: la transazione è indivisibile nella sua esecuzione e la sua esecuzione deve essere o totale o nulla, non sono ammesse esecuzioni parziali
  * Coerenza: quando inizia una transazione il database si trova in uno stato coerente e quando la transazione termina il database deve essere in un altro stato coerente
  * Isolamento: ogni transazione deve essere eseguita in modo isolato e indipendente dalle altre transazioni, l'eventuale fallimento di una transazione non deve interferire con le altre transazioni in esecuzione
  * Durabilità: detta anche persistenza, si riferisce al fatto che una volta che una transazione abbia richiesto un commit work, i cambiamenti apportati non dovranno essere più persi

### Introduzione a SQL
SQL è l'acronimo di Structured Query Language ed è il linguaggio di definizione e manipolazione dei dati universalmente usato nelle basi di dati relazionali. Essendo un linguaggio dichiarativo, SQL non richiede la stesura di sequenze di operazioni (come ad es. i Linguaggi imperativi), piuttosto di specificare le proprietà logiche delle informazioni ricercate. Esso si divide in:

* Query language (QL) - permette di interrogare il database, cioè di leggere i dati
* Data Definition Language (DDL) - permette di creare e cancellare database o di modificarne la struttura
* Data Manipulation Language (DML) - permette di inserire, cancellare, modificare i dati
* Data Control Language (DCL) - permette di gestire gli utenti e i permessi
* Device Media Control Language (DMCL) - permette di controllare i supporti (memorie di massa) dove vengono memorizzati i dati

<br>

## MODULO 2 (10:00-11:30; 24 Maggio): Primi passi con PostgreSQL

### Installare PostgreSQL

* Installazione di PostgreSQL su tutti i PC

### Principali elementi di PgAdmin
* Finestra principale
  * Descrizione dei pannelli
  * Descrizione dei principali elementi visualizzati all'interno di un database 
* Opzioni di visualizzazone
* Aggiunta di un nuovo server
  * Nome: database test
  * Host: 213.239.205.106
  * Porta: 5432
  * Utente: jrcuser
  * Password: -
* Interfaccia SQL
* Creare un nuovo database (**corso_postgres**)

### Regole di normalizzazione
La normalizzazione è un procedimento per l’eliminazione della ridondanza e del rischio di incoerenza dal database. Esistono vari livelli di normalizzazione (forme normali) basate
sul criterio che se una relazione presenta più concetti tra loro indipendenti, la si decompone in relazioni più piccole, una per ogni concetto. Regole delle prime 3 forme normali:

1. Ogni riga di ciascuna tabella deve poter essere identificata in modo univoco da un gruppo di dati in essa contenuti
2. Ogni colonna fa riferimento a dei dati atomici
3. I campi non chiave dipendono dall’intera chiave primaria e non da una parte di essa
4. I campi non chiave non dipendono da altri campi non chiave

### Tipi di dato
Ogni tipo di dato supporta un certo tipo di informazione e di operazioni permesse sui dati. E' una prima forma di garanzia per integrità dei dati.

* Numerici con precisione arbitraria
 * integer: intero con segno a 4 byte
 * bigint: intero con segno a 8 byte
 * smallint: intero con segno a 2-byte
 * numeric [(p, s)]: numerico di precisione selezionabile
 * double precision: numero a virgola mobile a doppia precisione (8 bytes)
 * serial: intero autoincrementale a 4-byte
 * bigserial: intero auto incrementale a 8 byte
* Booleani
 * boolean: valore Booleano (vero/falso)
* Caratteri (testo, varchar, char)
 * character varying [(n)]: stringa di caratteri a lunghezza variabile
 * character [(n)]: stringa di caratteri a lunghezza fissa
 * text: stringa di caratteri a lunghezza variabile
* Binari
 * bytea: dato binario («array di byte»)
* Data/ora 
 * time without time zone: orario del giorno (senza fuso orario)
 * time with time zone: orario del giorno, incluso il fuso orario
 * timestamp without time zone: data e orario (senza fuso orario)
 * timestamp with time zone: data e orario, includo il fuso orario
 * date: data di calendario (anno, mese, giorno)
* Altri tipi di dato
 * money: somma di denaro
 * xml: dati XML
 * point: punto geometrico 
 * line: linea 
 * polygon: tracciato chiuso
 * ...

### Sviluppare un modello dati

* In genere, lo sviluppo di un database relazionale ha tre fasi iniziali:
	
	1. Il livello **concettuale** rappresenta concetti e relazioni tra concetti. È completamente indipendente dal database che gestirà le strutture dati.
	2. Il livello **logico** genera un modello dettagliato, guidato dalle relazioni di significato tra i dati. È il livello di definizione delle tabelle in un DBMS relazionale, con indicazione di colonne e data type, chiavi primarie ed alternative, regole di integrità.
	3. Il livello **fisico** definisce le caratteristiche utili per l'ottimizzazione delle prestazioni e della memoria.  

**Discussione di un caso studio**

Un servizio di noleggio di DVD deve creare un database con l'elenco dei film collegato a una anagrafica degli attori, una lista di clienti e la registrazione di tutti i noleggi effettuati

<br>

## MODULO 3 (11:30-13:00; 24 Maggio): Costruire un database

### Creare uno schema
* Con PgAdmin
* Con SQL

Codice:

	CREATE SCHEMA data;

### Creare una tabella da interfaccia grafica

Tabella "DIPENDENTI" con nome, cognome, data_nascita, societa_nome, peso, sposato

Codice:

	CREATE TABLE data.dipendenti  
	  (nome character varying, 
	  cognome character varying, 
	  data_nascita date, 
	  societa_nome character varying, 
	  peso float, 
	  sposato BOOLEAN);

### Crea una chiave primaria
* Discussione su quali campi possono essere una chiave primaria
* Aggiunta di un campo serial
* Definizione della chiave

Codice:

	ALTER TABLE data.dipendenti ADD COLUMN dipendente_id SERIAL;
	ALTER TABLE data.dipendenti
	  ADD CONSTRAINT dipendenti_pkey PRIMARY KEY(dipendente_id);

### Creare una tabella con codice SQL
Tabella SOCIETA' [Nome, Settore commerciale, Numero dipendenti]

	CREATE TABLE data.societa
	  (societa_nome character varying,
	  settore character varying,
	  num_dipendenti integer);

	ALTER TABLE data.societa
	  ADD CONSTRAINT societa_pkey PRIMARY KEY(societa_nome);

### Popolare una tabella da interfaccia grafica
* Esempio con PgAdmin

Inserire utente: Aieie Brazu, nato il 3 dicembre 1987, lavora per la società ACME, pesa 66 chili e non è sposato.

### Popolare una tabella con SQL (INSERT INTO and VALUES)

	INSERT INTO data.dipendenti(nome, cognome, data_nascita, societa_nome, peso, sposato)
	  VALUES ('Gino', 'Pasticcino', '01-05-1978', 'ACME', 73, TRUE);

	INSERT INTO data.dipendenti(nome, cognome, data_nascita, societa_nome, peso, sposato)
	  VALUES ('Felice', 'Caccamo', '05-09-1951', 'ACME', 93, TRUE);

	INSERT INTO data.dipendenti(nome, cognome, data_nascita, societa_nome, peso, sposato)
	  VALUES ('Ciccio', 'Pasticcio', '01-04-1972', 'IQ s.p.a.', '79,4', FALSE);

	INSERT INTO data.dipendenti(nome, cognome, data_nascita, societa_nome, peso, sposato)
	  VALUES ('Grunnio', 'Corocotta', '21-01-1982', 'IQ spa', '65,4', TRUE);

	INSERT INTO data.dipendenti(nome, cognome, data_nascita, societa_nome, peso, sposato)
	  VALUES ('Ottone', 'Bugusciusciu', '11-12-1994', 'ACME', 67, FALSE);

### Popolare una tabella da un file csv
* Esempio con PgAdmin (file **dipendenti.csv**)  

Codice (il percorso del file deve essere adattato):

	COPY data.dipendenti (nome, cognome, data_nascita, societa_nome, peso, sposato)
	  FROM 'C:\corso_postgres\dipendenti.csv' WITH CSV DELIMITER ';';

* Esempio con SQL (file **societa.csv**)

Codice (il percorso del file deve essere adattato):

	COPY data.societa (societa_nome,settore,num_dipendenti) 
	  FROM 'C:\corso_postgres\societa.csv' WITH CSV DELIMITER ';';

### Esportare i dati in un file esterno
* Con PgAdmin (tabella dipendenti
* Usando SQL

Codice (il percorso del file deve essere adattato):

	COPY data.dipendenti
	  TO 'C:\corso_postgres\dipendenti_completo.csv' WITH CSV DELIMITER ';' HEADER;

### Creare commenti agli oggetti del database
* Importanza della documentazione

Codice inserimento descrizione:

	COMMENT ON TABLE data.dipendenti
	  IS 'Questa tabella è l''anagrafica dei dipendenti che aderiscono al progetto VinciUnTrilione';

### Creare vincoli sulla tabella
* Importanza della consistenza dei dati

Codice esempio:

	ALTER TABLE data.societa
	  ADD CONSTRAINT num_dipendenti_minimo
	  CHECK (num_dipendenti >= 0);

### Esercizio di ricapitolazione
* Crea una tabella con chiave primaria, inserire i dati

Creare una tabella per i dati contentuti nel file **caramelle_dipendenti.csv** dove sono riportate le informazioni su quante caramelle i dipendenti hanno mangiato ogni giorno nel 2015. Importare i dati, creare una chiave primaria, creare un vincolo sul valore caramelle (maggiore di 0 e minore di 100).

Tabella generata con:

	SELECT 
	  generate_series (1,13,1) AS dipendente_id, 
	  generate_series('2015-01-01'::date,'2015-12-31'::date,'1 day'::interval)::date as data,
	  (random()*10)::integer AS num_caramelle
	ORDER BY
	  random();

Soluzione:

	CREATE TABLE data.dipendenti_caramelle(
	  dipendente_id integer,
	  num_caramelle integer,
	  data date,
	  CONSTRAINT dipendenti_caramelle_pkey PRIMARY KEY (dipendente_id, data),
	  CONSTRAINT num_caramelle_range CHECK (num_caramelle >= 0 AND num_caramelle < 100));
	  
	COPY data.dipendenti_caramelle (dipendente_id,data,num_caramelle) 
	  FROM 'C:\corso_postgres\dipendenti_caramelle.csv' WITH CSV DELIMITER ';';

<br>

## MODULO 4 (14:00-16:30; 24 Maggio): SQL base 

### Principali comandi: SELECT, FROM, WHERE
* Esempi

Codice

	SELECT 
	  dipendenti.nome, 
	  dipendenti.cognome, 
	  dipendenti.societa_nome
	FROM 
	  data.dipendenti;

	SELECT 
	  *
	FROM 
	  data.dipendenti
	WHERE
	  peso > 75;

	SELECT 
	  societa_nome, 
	  settore, 
	  num_dipendenti
	FROM 
	  data.societa
	WHERE
	 settore = 'Ristorazione';

* Esercizio

Selezionare tutti i dipendenti della società ACME.

### Altri comandi base (1): AND, OR, LIMIT, ORDER BY
* Esempi

	SELECT 
	  *
	FROM 
	  data.dipendenti
	WHERE
	  peso > 75 AND societa_nome = 'ACME';

	SELECT 
	  *
	FROM 
	  data.dipendenti
	WHERE
	  peso > 75 OR societa_nome = 'ACME';

	SELECT 
	  *
	FROM 
	  data.dipendenti
	WHERE
	  peso IS NULL;

	SELECT 
	  *
	FROM 
	  data.dipendenti
	WHERE
	  peso < 75 AND sposato
	ORDER BY peso;

	SELECT 
	  *
	FROM 
	  data.dipendenti
	WHERE
	  NOT sposato AND data_nascita > '01-01-1979'
	ORDER BY 
	  peso DESC
	LIMIT 4;

* Esercizio
	1. Fai una interrogazione per avere i 2 dipendenti più leggeri della società SmartPuccino che o non sono sposati o hanno meno di 40 anni.  
	2. A quale società appartiene il dipendente più pesante?

### Altri comandi base (2): UPDATE, DELETE
	UPDATE 
	  data.dipendenti
	  SET 
	    peso=peso-1
	 WHERE 
	   NOT sposato;

	INSERT INTO data.dipendenti(nome, cognome, data_nascita, societa_nome, peso, sposato)
	  VALUES ('PIPPO', 'test', '01-05-1901', 'ACME', 99, TRUE);

	DELETE FROM data.dipendenti
	  WHERE cognome = 'test';

### Uso di ALIAS
	SELECT 
	  mytable.societa_nome AS nome, 
	  mytable.settore AS settore_commerciale, 
	  mytable.num_dipendenti 
	FROM 
	  data.societa AS mytable;

### Combinare i campi numerici e di testo
* Esempi

Codice: 

	SELECT 
	  nome || ' ' || cognome AS nome_completo,
	  data_nascita, 
	  data_nascita + 1 as giorno_dopo, 
	  substring(societa_nome,1,3), 
	  peso * 4 - 2 peso_sballato
	FROM 
	  data.dipendenti;

* Esercizio

Visualizzare il quadrato del numero dei dipendenti delle società che operano nella ristorazione.

### Comando DISTINCT
* Esempi

Codice:
	
	SELECT 
	  nome
	FROM 
	  data.dipendenti
	ORDER BY
	  nome;
	
	SELECT DISTINCT
	  nome
	FROM 
	  data.dipendenti
	ORDER BY
	  nome;

* Esercizio

Visualizzare tutti i nomi di società dalla tabella **data.dipendenti**. 

### Comando UNION

	SELECT distinct  societa_nome
	FROM data.dipendenti
	Where peso > 80
		UNION
	SELECT societa_nome
	FROM data.societa
	WHERE num_dipendenti < 20;

<br>

## MODULO 5 (16:30-17:30; 24 Maggio): Estendere il database

### Uso di indici

	CREATE INDEX societa_dipendenti_index
	  ON data.dipendenti
	  USING btree
	  (societa_nome);

### Creare una chiave esterna (integrità referenziale)

	ALTER TABLE data.dipendenti
	  ADD CONSTRAINT dipendenti_societa_fkey FOREIGN KEY (societa_nome)
	  REFERENCES data.societa (societa_nome) MATCH SIMPLE
	  ON UPDATE NO ACTION ON DELETE NO ACTION;

Se esistono valori non referenziati nell'altra tabella, la chiave non funziona.

Correggere il valore scorretto:

	UPDATE 
	  data.dipendenti
	SET 
	  societa_nome='IQ spa'
	WHERE 
	 societa_nome='IQ s.p.a.';

* Esercizio

Creare una chiave esterna per il campo dipendenti_id della tabella data.caramelle_dipendenti verso la tabella data.dipendenti.

	ALTER TABLE data.dipendenti_caramelle
	  ADD CONSTRAINT dipendenti_caramelle_fkey FOREIGN KEY (dipendente_id)
	  REFERENCES data.dipendenti (dipendente_id) MATCH SIMPLE
	  ON UPDATE NO ACTION ON DELETE NO ACTION;

### Viste

	CREATE VIEW data.view_dipendenti_sposati AS
	  SELECT * FROM data.dipendenti WHERE sposati;

	SELECT * FROM data.view_dipendenti_sposati;

### Crea una tabella da una query

	CREATE TABLE data.tabella_dipendenti_sposati AS
	  SELECT * FROM data.dipendenti WHERE sposati;

	SELECT * FROM data.view_dipendenti_sposati;

<br>

## MODULO 6 (09:00-11:30; 25 Maggio): SQL intermedio - 1

### Interrogare più tabelle: JOIN

* Esempio da interfaccia grafica

Codice:

	SELECT 
	  dipendenti.nome, 
	  dipendenti.cognome, 
	  societa.societa_nome, 
	  societa.settore
	FROM 
	  data.dipendenti, 
	  data.societa
	WHERE 
	  societa.societa_nome = dipendenti.societa_nome;

	SELECT 
	  dipendenti.nome, 
	  dipendenti.cognome, 
	  societa.societa_nome, 
	  societa.settore
	FROM 
	  data.societa
	JOIN 
	  data.dipendenti
	ON 
	  societa.societa_nome = dipendenti.societa_nome
	WHERE
	  sposato;

### Funzioni di aggregazione: GROUP BY
* Esempi

Calcolare il numero medio di caramelle  mangiate da ogni dipendente e il numero totale, ordinando dal dipendente più goloso a quello meno goloso

	SELECT 
	  dipendente_id, 
	  avg(num_caramelle) AS medio,  
	  sum(num_caramelle) AS totale
	FROM 
	  data.dipendenti_caramelle
	GROUP BY 
	  dipendente_id
	ORDER by totale DESC;

Calcolare il numero di dipendenti nel database per ogni società

	SELECT 
	  societa_nome, 
	  count(*) numero_totale, 
	  count(peso) numero_peso_non_nullo
	FROM 
	  data.dipendenti
	GROUP BY 
	  societa_nome;

Calcolare il peso medio e il numero di dipendenti di ogni società

	SELECT 
	  a.societa_nome, 
	  avg(b.peso)::integer AS peso_medio,
	  count(*) AS num_dipendenti_lista
	FROM 
	  data.societa a
	JOIN 
	  data.dipendenti b
	ON 
	  a.societa_nome = b.societa_nome
	GROUP BY
	  a.societa_nome;

### Altri tipi di JOIN: LEFT (RIGHT, FULL)
* Esempio

Calcolare il numero di dipendenti monitorati per tutte le società nella tabella **data.societa**, comprese le società senza dipedenti nella tabella **data.dipendenti**.

		SELECT 
		  a.societa_nome, 
		  count(cognome) AS num_dipendenti_monitorati
		FROM 
		  data.societa a
		LEFT JOIN 
		  data.dipendenti b
		ON 
		  a.societa_nome = b.societa_nome
		GROUP BY
		  a.societa_nome;

### Clausola HAVING
* Esempio

Calcolare il peso medio dei dipendenti di ogni società ma solo per le società dove il peso medio è maggiore di 70 kg.

	SELECT 
	  a.societa_nome, 
	  avg(b.peso)::integer AS peso_medio,
	  count(*) AS num_dipendenti_lista
	FROM 
	  data.societa a
	JOIN 
	  data.dipendenti b
	ON 
	  a.societa_nome = b.societa_nome
	GROUP BY
	  a.societa_nome
	HAVING 
	  avg(b.peso) > 70;

### Esercizi di ricapitolazione

1. Creare una view con i nomi dei dipendenti che pesano più di 70 chili visualizzando il settore delle loro società
2. Calcolare il numero medio di caramelle mangiato da ogni dipendente.
3. Calcolare il numero totale dei dipendenti per settore dove il numero di dipendenti è maggiore di 5

<br>

## MODULO 7 (11:30-13:00; 25 Maggio): SQL intermedio - 2

### Sub-query
* Esempi

Selezionare il nome e il cognome di tutti i dipendenti della società con più dipendenti nella tabella **data.dipendenti**

	SELECT 
	  nome, cognome, dipendenti.societa_nome
	FROM data.dipendenti,
		(SELECT 
		  societa_nome, 
		  count(*)
		FROM 1
		  data.dipendenti
		group by 
		  societa_nome
		ORDER BY 
		  count(*) desc
		LIMIT 1) a
	WHERE
	  a.societa_nome = dipendenti.societa_nome;

### Plain SQL: comando WITH
* Esempi

Stesso problema dell'esempio precedente

	WITH tabellax AS
	(SELECT 
	  societa_nome, 
	  count(*)
	FROM 
	  data.dipendenti
	group by 
	  societa_nome
	ORDER BY 
	  count(*) desc
	LIMIT 1)
	
	SELECT 
	  nome, cognome, dipendenti.societa_nome
	FROM 
	  data.dipendenti,
	  tabellax
	WHERE
	  tabellax.societa_nome = dipendenti.societa_nome;

### Cambiare tipo di dato

	SELECT 
	  5/2, 
	  (5::float/2), 
	  (5::float/2)::integer, 
	  '10'::character varying, 
	  '10'::integer, 
	  substr('ciao100',5,7), 
	  substr('ciao100',5,7)::integer;

	SELECT 'a'::integer;

### Alcune funzioni speciali

**generate_series()**

	SELECT generate_series(1,10,1);

	SELECT generate_series(6,20,2);

**now()**

	SELECT now();

**random()**

	SELECT random();

	SELECT generate_series(1,100,1), (random()*10)::integer;

**coalesce()**

	SELECT 
	  a.societa_nome, 
	  coalesce(count(cognome),0) AS num_dipendenti_monitorati
	FROM 
	  data.societa a
	LEFT JOIN 
	  data.dipendenti b
	ON 
	  a.societa_nome = b.societa_nome
	GROUP BY
	  a.societa_nome;

### Tipi di dato temporali

**Date, Time, Timestamp**

	SELECT now()::date;

	SELECT now()::time;

	SELECT '1-1-2010'::timestamp;

**Time zone**

	SELECT '1-1-2010'::timestamp without time zone;

	SELECT 
	  now(), 
	  now()::timestamp at time zone 'UTC',
	  now()::timestamp at time zone 'CDT';

**Extract part of a date**

	SELECT 
	  EXTRACT (MONTH from now()),
	  EXTRACT (day from now()),
	  EXTRACT (DOY from now()),
	  EXTRACT (epoch from now());

**Interval between two dates**

	SELECT now()::date - '1-1-2015'::date;
	
	SELECT now() - '1-1-2015'::timestamp;


### Ricerca su tipi di dato testo

	SELECT nome FROM data.dipendenti WHERE nome LIKE 'G';
	
	SELECT nome FROM data.dipendenti WHERE nome LIKE 'G%';
	
	SELECT nome FROM data.dipendenti WHERE nome LIKE '_i%';	
	
	SELECT nome FROM data.dipendenti WHERE nome LIKE '%i%';	

### Valori codificati

Il campo "settore" potrebbe essere rappresentato da un codice che fa riferimento a una tabella con la lista completa dei valori ammessi (tabella di look up), in modo da avere dati sempre consistenti. Una soluzione alternativa è creare una serie di constraint sui valori del campo (esempio: maschio/femmina)

### Esercizio di ricapitolazione

1. Trovare il numero massimo di caramelle mangiato in un giorno
2. Calcolare il numero medio di caramelle mangiato da ogni dipendente a maggio
2. Calcolare il numero medio di caramelle mangiato da ogni dipendente in ogni mese
3. Calcolare il numero medio di caramelle mangiato dai dipendenti di ogni società
4. Calcolare l'età di ogni dipendente

<br>

## MODULO 8 (14:00-15:30; 25 Maggio): SQL avanzato

### Funzioni window


* Esempi

Vedere per ogni dipendente se il peso è maggiore o minore del peso dei dipendenti della stessa azienda e la classifica per ogni azienda
	
	SELECT 
	  nome, 
	  cognome, 
	  peso, 
	  avg(peso) over(partition by societa_nome) peso_medio,  
	  peso - avg(peso) over(partition by societa_nome) differenza_peso,
	  rank() OVER (partition by societa_nome order by peso DESC) posizione,   
	  societa_nome 
	FROM 
	  data.dipendenti
	ORDER by societa_nome, peso DESC;

* Esercizi

	1. Fare la classifica dal più pesante al meno pesante dei dipendenti sposati e non sposati
	2. Calcolare la percentuale del peso di ogni dipendente sul totale dei dipendenti della sua azienda
	3. Calcolare la percentuale di caramelle mangiate da ogni dipendente sul totale delle caramelle mangiate dai dipendenti della stessa azienda

* Tablefunc

Visualizzare i dati da vettori a matrice (12 colonne, una con ogni mese) per tutti i dipendnti con numero totale di caramelle mangiate.

	CREATE EXTENSION tablefunc;
 
	SELECT 
	  dipendente_id,
	  crosstab.mon_1,
	  crosstab.mon_2,
	  crosstab.mon_3,
	  crosstab.mon_4,
	  crosstab.mon_5,
	  crosstab.mon_6,
	  crosstab.mon_7,
	  crosstab.mon_8,
	  crosstab.mon_9,
	  crosstab.mon_10,
	  crosstab.mon_11,
	  crosstab.mon_12
	FROM 
	  crosstab(
	  'SELECT 
	    dipendente_id, 
	    ''mon_'' ||extract(month from data) AS mese, 
	    sum(num_caramelle) AS caramelle
	  FROM 
	    data.dipendenti_caramelle
	  GROUP BY
	    dipendente_id, mese
	  ORDER BY 
	    dipendente_id, mese'::text, 'SELECT ''mon_'' || a from generate_series(1,12,1) a'::text) crosstab(dipendente_id integer, 
		mon_1 integer, mon_2 integer, mon_3 integer, mon_4 integer, mon_5 integer, mon_6 integer, mon_7 integer, mon_8 integer, 
		mon_9 integer, mon_10 integer, mon_11 integer, mon_12 integer);


<br>

## MODULO 9 (15:30-17:00; 25 Maggio): Strumenti di sviluppo del database (opzionale)

### Stored procedures

Una funzione è un codiceche viene implementato all'interno del database utilizzando SQL o un altro linguaggio (ad esempio PSQL, Python, C). Le funzioni consentono di creare processi complessi e algoritmi che  SQL da solo non può fare. Una volta creata, una funzione diventa parte della libreria dei comandi del database e può essere chiamata all'interno di una query SQL.

	CREATE SCHEMA tools;
	
	COMMENT ON SCHEMA tools 
	  IS 'Schema che contiene tutte le funzioni e i vari strumenti.';

	CREATE FUNCTION tools.test_add(integer, integer) 
	  RETURNS integer AS 'SELECT $1 + $2;'
	  LANGUAGE SQL
	  RETURNS NULL ON NULL INPUT;

	SELECT tools.test_add(28,13);

### Trigger e funzioni trigger

Un trigger fa si che il database esegua automaticamente una particolare funzione ogni volta che viene eseguito un certo tipo di operazione su una tabella.

	ALTER TABLE data.dipendenti 
	  ADD COLUMN update_timestamp timestamp with time zone DEFAULT now();

	CREATE OR REPLACE FUNCTION tools.timestamp_last_update()
	  RETURNS trigger AS
	  $BODY$BEGIN
	    IF NEW IS DISTINCT FROM OLD THEN
	      NEW.update_timestamp = now();
	    END IF;
	  RETURN NEW;
	  END;$BODY$;

	CREATE TRIGGER update_timestamp
	  BEFORE UPDATE
	  ON main.data.dipendenti
	  FOR EACH ROW
	  EXECUTE PROCEDURE tools.timestamp_last_update();

<br>

## MODULO 10 (17:00-17:30; 25 Maggio): Uso avanzato del database (opzionale)

### Tipi di dato spaziale
* PostGIS

### Altri tipi di dato
* Array, immagini

### Connettersi al database con altri client
* phpPgAdmin, Excel, Access, LibreOffice, R

### Altri linguaggi procedurali
* Pl/pgsql, Pl/R

<br>

## AMMINISTRAZIONE DEL DATABASE (09:00-15:30; 26 Maggio)

### Interagire con il database da riga di comando: psql
### Gestione degli utenti e dei permessi
### Configurazione database
### Otimizzazione database
### Backup e ripristino
### VACUMM
### Verificare dimensione di un database, schema, tabella
### Otimizzazione delle query
### Tablespace
### Esercizio di ricapitolazione finale