# command : locate

Maintains db for faster lookups of files

```bash
locate file.png
```

- if we create new file and then running locate command doesn't show us that file's location
- we have to update db of that locate command manually by running 

```bash
sudo updatedb
```

**how to change timer for updation of db for locate command**

```bash
systemctl list-timers | grep mlocate
```

* if there is no results then timer is configured in cron job

```bash
cd /etc/cron.daily
```

### flags in locate

#### locate with particular base name
```bash
locate -b '\filename.txt'
```

#### count number of files or folders that matches given pattern

```bash
locate -c 
```

#### for case insensitive search

```bash
locate -i filename.txt
```

#### for limited number of search
```bash
locate -l 5
```


#### for regrex 
```bash
locate --regex '/kill\.md$'
```

\ = escape char for .