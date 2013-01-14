snapshot.sh
===========

Rotating rsync backups, intended for use with OS X (tested with 10.8).

### Config

Edit the scipts to set source/destication directories to match you desires, and edit to control how many backups to keep.


### Make Executable

Move the scripts to somewhere on your path.

    cp snapshot /usr/local/bin/ && cp snapshot_daily_rotate /usr/local/bin/
    cp backup_exclude /usr/local/etc/

### Cron

Add these tasks to your `root` cron

    0 */4 * * * /usr/local/bin/snapshot >/dev/null 2>&1
    0 0 * * *  /usr/local/bin/snapshot_daily_rotate

### Next Steps

I plan on re-working these scripts to allow better cusomtization, specifically to allow arguements to the script

** I will likely do this with [methadone](https://github.com/davetron5000/methadone) or [gli](https://github.com/davetron5000/gli)**


#### Thanks to

* Mike Rubel's (old but) very nice article on "[Easy Automated Snapshot-Style Backups with Linux and Rsync] (http://www.mikerubel.org/computers/rsync_snapshots/)"
