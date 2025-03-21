# Comandi
Raccolta di comandi generalmente utili per varie task

<details>

<summary> PostgreSQL & PGAdmin4 </summary>

### Installazione PostgreSQL (*Linux*)
https://www.postgresql.org/download/linux/debian/

### Installazione PGAdmin4 (*Linux*)
https://www.pgadmin.org/download/pgadmin-4-apt/

### Comandi vari per *Windows*
https://www.microfocus.com/documentation/idol/IDOL_12_0/MediaServer/Guides/html/English/Content/Getting_Started/Configure/_TRN_Set_up_PostgreSQL.htm

### Comandi per *Linux*

- Modificare password utente (tutto il pc):
```terminal
sudo passwd nomeUtente
```
- Entrare nella sessione con postgres:
```terminal
su - postgres
```
- Dentro la sessione, per modificare la password del ruolo:
```terminal
psql -c "ALTER USER userName WITH PASSWORD 'password';"
```
- Creare un database e garantire tutti i privilegi ad un utente:
```sql
CREATE DATABASE nomeDB;
```
```sql
--non ancora proprietario del database
GRANT ALL ON DATABASE nomedb TO nomeuser;
```
- Cambiare proprietario del database:
```sql
ALTER DATABASE nomedb OWNER TO nomeuser;
```
- Creazione di un nuovo utente:
```sql
CREATE USER nomeutente WITH PASSWORD 'password';
```
- Funzione che permette di eliminare tutti i dati da tutte le tabelle senza cancellarle
```sql
CREATE OR REPLACE FUNCTION cancella(username IN VARCHAR) RETURNS void AS $$
DECLARE
    statements CURSOR FOR
        SELECT tablename FROM pg_tables
        WHERE tableowner = username AND schemaname = 'azienda';
BEGIN
    FOR stmt IN statements LOOP
        EXECUTE 'TRUNCATE TABLE azienda.' || quote_ident(stmt.tablename) || ' CASCADE;';
    END LOOP;
END;
$$ LANGUAGE plpgsql;
```

### Lista funzioni oracle
https://www.oracletutorial.com/oracle-string-functions/

### Tutorial ruoli e permessi
https://www.digitalocean.com/community/tutorials/how-to-use-roles-and-manage-grant-permissions-in-postgresql-on-a-vps-2

</details>

<details>

<summary>Java</summary>

### Fonti
- Java tutorials (per apprendere) 
	https://docs.oracle.com/javase/tutorial/
- Java API Documentation (per consultare ogni classe) 
	https://docs.oracle.com/en/java/javase/21/docs/api/index.html
- Java Specifiche (per chiarire dubbi tecnici)
  	https://docs.oracle.com/javase/specs/

</details>

<details>
	
<summary> Git </summary>

### Tutorial uso comandi add, commit, push etc...
https://www.atlassian.com/git/tutorials/saving-changes?section=git-add

### Configurazione credenziali utente tramite git
https://linuxhint.com/git-log-out-user-from-command-line/#:~:text=To%20log%20out%20from%20the%20Git%20command%20line%2C%20first%2C%20move,config%20%E2%80%93global%20%E2%80%93unset%20user.

### Eliminazione di una commit dalla history tramite bash
```git
git reset --soft HEAD~numerocommitdaeliminarepartendodallatesta
```
Per inviare i cambiamenti alla origin source:
```git
git push origin +main --force
```
### Overview git-credential-manager
https://github.com/git-ecosystem/git-credential-manager/blob/main/README.md

### Installazione git-credential-manager
https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md

### Configurazione git-credential-manager
https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/credstores.md
oppure
```
git config --global credential.credentialStore secretservice
```

</details>

<details>
	
<summary> GitHub </summary>

### Tutorial markup language
https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

</details>

<details>
	
<summary> Windows11 </summary>

### Attivazione
https://github.com/massgravel/Microsoft-Activation-Scripts

### Comandi CMD
https://www.freecodecamp.org/italian/news/lista-di-comandi-per-il-prompt-un-tutorial-per-la-riga-di-comando/#:~:text=Puoi%20usare%20il%20comando%20echo,echo%20contenuto%2Dfile%20%3E%20nomefile.

</details>

<details>

<summary> Linguaggio JAVA </summary>
	
### Installazione JAVA
1) link procedura generale: https://ubuntuhandbook.org/index.php/2022/03/install-jdk-18-ubuntu/

2) Scaricare la versione di java più recente ed installare tramite package manager: https://www.oracle.com/java/technologies/downloads/
	
3) Scaricare "jdk-20-scripts.sh" (aggiornato alla più recente jdk-20)

4) Nella shell di un SO debian-based: ```bash jdk-20-scripts.sh```
	
5) Nel caso non si fosse ancora concretizzata, utilizzare ```sudo update-alternatives --config java``` e selezionare la versione appena installata
	
### Configurazione driver JDBC per postgresql
https://jdbc.postgresql.org/
	
</details>

<details>
	
<Summary> JSON </Summary>
	
### Integrazione JSON in java
 
https://www.baeldung.com/java-org-json
 
</details>

<details>

<Summary> Eclipse </Summary>

### Problemi kotlin compiler con classe java.Serializable
Aggiornare il path della variabile JDK_Home seguendo il percorso: Window -> Preferences -> Kotlin -> Compiler -> nella voce JDK Home settare path adeguato

</details>
