# Comandi
Raccolta di comandi generalmente utili per varie task

<details>

<summary> PostgreSQL & PGAdmin4 </summary>

### Installazione PostgreSQL (*Linux*)
https://www.how2shout.com/linux/install-postgresql-server-client-on-ubuntu-22-04-lts-jammy/

### Installazione PGAdmin4 (*Linux*)
https://www.how2shout.com/linux/how-to-install-pgadmin-4-on-ubuntu-20-04-lts-linux/

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

</details>

<details>
	
<summary> GitHub </summary>

### Tutorial markup language
https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

</details>

<details>
	
<summary> Attivazione Windows11 </summary>
https://github.com/massgravel/Microsoft-Activation-Scripts

</details>

<details>

	<summary> Linguaggio JAVA </summary>
	Esempiooooo
	
</details>