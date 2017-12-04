Ansible role for Supervisor install on Amazon Linux
---

Ansible role for Supervisor install on Amazon Linux, CentOS 6/7.

# Role variables

```yaml
supervisor_user: root                                       # default user
supervisor_sock: /var/run/supervisor.sock                   # path to your socket file
supervisor_conf_file: /etc/supervisord.conf                 # path to your conf file
supervisor_pidfile: /var/run/supervisord.pid                # pidfile location
supervisor_programs_dir: /etc/supervisor/conf.d/            # child programs location
supervisor_childlogdir: /var/log/supervisor/                # where child log files will live
supervisor_logfile: /var/log/supervisor/supervisor.log      # supervisord log file
supervisor_logfile_maxbytes: 50MB                           # maximum size of logfile before rotation
supervisor_logfile_backups: 10                              # number of backed up logfiles
supervisor_loglevel: debug                                  # info, debug, warn, trace
supervisor_nodaemon: false                                  # run supervisord as a daemon
supervisor_minfds: 1024                                     # number of startup file descriptors
supervisor_minprocs: 200                                    # number of process descriptors
```

# Dependencies

* Mallear.yum

# Example

```yml
---
- hosts: localhost
  remote_user: root
  become: yes
  roles:
  - Mallear.supervisord-aws-linux
```