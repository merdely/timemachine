# timemachine backup

## Background

**timemachine backup** uses rsync to create backups. It uses rsync's
`--link-dest` feature to create hard links to the last backup's files if
they have not changed

## Configuration

### Backup Server

Create /etc/timemachine/config
Use config.example as a guide to create a configuration that suits your needs

### Backup Clients

#### What to back up

Create /etc/timemachine/backup_list, which is a list of mount points/directories
to back up

Note that **timemachine backup** does not cross filesystem boundaries. So if
/path/to/filesystem1 and /path/to/filesystem1/filesystem2 are different file
systems, they both must be in backup_list to be backed up

#### What to ignore

Create /etc/timemachine/exclude_list, which is a list of files and directories
to exclude from the backup

