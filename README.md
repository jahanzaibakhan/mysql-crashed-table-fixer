# mysql-crashed-table-fixer

Interactive script that fixes crashed MyISAM tables (`ENGINE NULL`, "marked as crashed and last repair failed") on MySQL/MariaDB servers.

Steps: check access -> ask DB + table name(s) -> backup table files -> `REPAIR TABLE` (falls back to `USE_FRM`) -> convert to InnoDB -> show status and fixed tables.

```bash
bash fix_crashed_tables.sh
```

Run as root or a sudo user. Backups go to `/root/mysql_table_backups/<db>_<timestamp>/`.
