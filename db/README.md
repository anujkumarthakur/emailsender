# EmailSender

EmailSender is a Golang Software for sending the Emails to User as their Location Time on exact 8:00AM.

## Installation

### Setup The database

```bash
mysql -u username -p
```

```bash
create database emailsender
```

```bash
use emailsender
```

Provide the directory location of database file

```bash
source /home/user/filename.sql
```

Use the Command to Initialize go mod [go mod init emailsender].

Provide the Credentials into [emailsender.service] file.

Send the emailsender.service file to [lib/systemd/system/] this Location.
