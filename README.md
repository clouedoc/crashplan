# crashplan

Backup plan for my personal data.

## Requirements

- A 1TB HDD
  - Optionally, it can be encrypted.
- A computer
- Google Drive account with unlimited storage (.edu account) *(or any other remote storage provider really)*

## How to run ?

1. Connect a 1TB HDD to your computer
2. Edit `.env` with your HDD's mountpoint.
3. Start Duplicati and Syncthing with `docker-compose up -d`

## Web interfaces

Syncthing: <http://127.0.0.1:8384/>
Duplicati: <http://localhost:8200/>

## How to load data in this setup

TODO

## Roles of Duplicati and Syncthing

### Syncthing

Syncthing allows us to easily sync data between devices and the HDD.
The server can act as a relay to sync data between devices.

### Duplicati

Duplicati takes the data synced from Syncthing and backs it up to Google Drive

## Health checks

You will need to periodically check the health of your installation.

This includes checking that:

1. your Google Drive account is still storing your backups
2. Duplicati is still doing periodic backups
3. Syncthing is still syncing from other devices

## Risks

### Losing backups in time

If Google Drive closes your account, you will loose your backups, but your data will still be there.
You won't be able to load older backups as only the most recent data is stored locally.
To mitigate this risk, you can backup your data to multiple cloud providers.

### Data being seized locally

Someone can steal your HDD and read your data.
This can be mitigated by encrypting your HDD.

## More information

Learn more about the [3-2-1 backup rule](https://www.nakivo.com/blog/3-2-1-backup-rule-efficient-data-protection-strategy/).

## License

MIT License.
