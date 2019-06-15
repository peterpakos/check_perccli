# check_perccli
Nagios/Opsview plugin to check status of PowerEdge RAID Controller using PERCCLI utility

If you spot any problems or have any improvement ideas then feel free to open
an issue and I will be glad to look into it for you.

## Installation
The script `check_perccli` is normally copied to Nagios/Opsview plugins directory (/usr/local/nagios/libexec/).

## Usage - Help
```
$ check_perccli --help
usage: check_perccli [--version] [-h] [--debug] [--verbose] [--quiet] -H HOST
                     [-P PORT] [-u USERNAME] [-p PASSWORD] [-k SSH_KEY]
                     [-c PERCCLI_PATH]

Nagios plugin to check status of PowerEdge RAID Controller using PERCCLI
utility

optional arguments:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  --debug               debugging mode
  --verbose             verbose debugging mode
  --quiet               no console output
  -H HOST, --host HOST  server hostname or IP address
  -P PORT, --port PORT  SSH port (default: 22)
  -u USERNAME, --username USERNAME
                        SSH username (default: root)
  -p PASSWORD, --password PASSWORD
                        SSH password (overrides publickey auth)
  -k SSH_KEY, --ssh-key SSH_KEY
                        SSH private key (default: ~/.ssh/id_rsa)
  -c PERCCLI_PATH, --perccli-path PERCCLI_PATH
                        Path to perccli (default: /opt/lsi/perccli/perccli)
```