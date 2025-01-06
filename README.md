# simple-rsync-backup

Simple rsync-based backup. Can be used to rsync to a locally attached
or remotely attached HDD.


## Configuration

You can output help on the available parameters using the `-h` flag:

```bash
./simple_backup.sh -h
```

### simple_backup.list

Lists the backups to perform. Uses tab-separated triplets:

```
BACKUPNAME <TAB> SOURCEDIR <TAB> TARGETDIR
```

### simple_backup.BACKUPNAME.excl

For each `BACKUPNAME` in `simple_backup_list`, you can (optionally) 
specify excluded resources (files/dirs).


## Examples

### Local HDD

The following will perform the backup onto the HDD `backup_hdd` mounted for the
user under `/media/USER` into directory `backup`:

```bash
./simple_backup.sh -b /media/USER/backup_hdd/backup -d -v
```

### Remote HDD

The following will perform the backup into directory `backup` onto the remote HDD mounted
on `BACKUPSERVER` under `/media/MOUNTPOINT`:

```bash
simple_backup.sh -b /media/MOUNTPOINT/backup -d -v -H BACKUPSERVER -u BACKUPUSER -P
```

The backup will run as user `BACKUPUSER`, with the user being prompted to enter 
a password (`-P`).

