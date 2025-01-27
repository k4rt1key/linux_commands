# commands: cron

- To edit the cron jobs for the current user, run the following command:

```bash
crontab -e
```

```
* * * * * /path/to/command
│ │ │ │ │
│ │ │ │ │
│ │ │ │ └── Day of the week (0 - 7) (Sunday is both 0 and 7)
│ │ │ └──── Month (1 - 12)
│ │ └────── Day of the month (1 - 31)
│ └──────── Hour (0 - 23)
└────────── Minute (0 - 59)
```

- Add command 
```bash
* * * * * /path/to/command
```


```bash
crontab -l # lists all jobs
crontab -r # remove all jobs
```

