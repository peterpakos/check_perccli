# check_perccli
Nagios/Opsview plugin to check status of PowerEdge RAID Controller using PERCCLI utility

If you spot any problems or have any improvement ideas then feel free to open
an issue and I will be glad to look into it for you.

## Installation
The script `check_perccli` is normally copied to Nagios/Opsview plugins directory (/usr/local/nagios/libexec/).

## Usage
Sample output:
```
$ check_perccli -H esxi01.example.com -p password
OK - C0: Optimal, PD0: Onln, PD1: Onln, PD2: Onln, PD3: Onln, VD0: Optl, BBU: Optimal
$ echo $?
0
```
Debug output:
```
$ check_perccli -H esxi01.example.com -p password --debug
2019-06-16 01:06:13 [check_perccli] DEBUG Namespace(debug=True, host='esxi01.example.com', password='password', perccli_path='/opt/lsi/perccli/perccli', port='22', ssh_key='~/.ssh/id_rsa', username='root', verbose=False)
2019-06-16 01:06:14 [check_perccli] DEBUG SSH connection established
2019-06-16 01:06:16 [check_perccli] DEBUG Controllers: 1
2019-06-16 01:06:16 [check_perccli] DEBUG C0: PERC H710 Adapter (Optimal)
2019-06-16 01:06:16 [check_perccli] DEBUG C0 Physical Drives: 4
2019-06-16 01:06:16 [check_perccli] DEBUG C0 PD0: TOSHIBA HDWD130 2.728 TB (Onln)
2019-06-16 01:06:16 [check_perccli] DEBUG C0 PD1: TOSHIBA HDWD130 2.728 TB (Onln)
2019-06-16 01:06:16 [check_perccli] DEBUG C0 PD2: TOSHIBA HDWD130 2.728 TB (Onln)
2019-06-16 01:06:16 [check_perccli] DEBUG C0 PD3: TOSHIBA HDWD130 2.728 TB (Onln)
2019-06-16 01:06:16 [check_perccli] DEBUG C0 Virtual Drives: 1
2019-06-16 01:06:16 [check_perccli] DEBUG C0 VD0: RAID10 (Optl)
2019-06-16 01:06:16 [check_perccli] DEBUG C0 BBU (Optimal)
2019-06-16 01:06:16 [check_perccli] INFO OK - C0: Optimal, PD0: Onln, PD1: Onln, PD2: Onln, PD3: Onln, VD0: Optl, BBU: Optimal
```

## Help
```
$ check_perccli --help
usage: check_perccli [--version] [-h] [--debug] [--verbose] -H HOST [-P PORT]
                     [-u USERNAME] [-p PASSWORD] [-k SSH_KEY]
                     [-c PERCCLI_PATH]

Nagios/Opsview plugin to check status of PowerEdge RAID Controller using
PERCCLI utility

optional arguments:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  --debug               debugging mode
  --verbose             verbose debugging mode
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
