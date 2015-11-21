## SIMP modulesync config

This repository contains management rake tasks and common module assets for [SIMP](), for use with [modulesync](https://github.com/puppet-community/modulesync).

- [Warnings](#warnings)
  * [THIS TOOL OVERWRITES FILES!](this-tool-overwrites-files)
  * [Beware `modulesync`'s dangerous quirks](#beware-modulesyncs-dangerous-quirks)
- [Usage](#usage)
- [Managed Assets](#managed-assets)
- [Managed Modules](#managed-modules)
- [Unmanaged Modules](#unmanaged-modules)

## Warnings
Before using this tool, there are some things you should know:

### THIS TOOL OVERWRITES FILES!
**All** [managed assets](#managed-assets) in **all** [managed modules](#managed-modules) will be replaced!  Which is the point of this project.

### Beware `modulesync`'s dangerous quirks
`modulesync` has several quirks than can be **very** dangerous to the unwary.  If you read `modulesync`'s [README.md](https://github.com/puppet-community/modulesync/blob/master/README.md), you will quickly notice that by default, `msync` will push all assets right back onto the `master` branch of the original repository!  It does not suport separate remote repositories to pull from and push to.  


## Usage
```bash
# Installs gems
bundle update

# check out all modules, change to feature branch 'SIMP-XXX' (i.e., your Jira
# issue), and whack in all common files.
msync update  --noop --branch SIMP-XXX

# TODO: rake tasks to:
#  - validate changes
#  - fork repos (if needed)
#  - add remotes (if needed)
#  - push changes
#  - submit Pull Requests
```

## Managed Assets
```
moduleroot/
├── CONTRIBUTING.md
├── Gemfile
├── .puppet-lint.rc
├── Rakefile
├── .rspec
└── .travis.yml
```


## Managed Modules
We only manage assets for modules maintained by the SIMP team.  These include:

- pupmod-simp-acpid
- pupmod-simp-activemq
- pupmod-simp-aide
- pupmod-simp-apache
- pupmod-simp-auditd
- pupmod-simp-autofs
- pupmod-simp-clamav
- pupmod-simp-concat
- pupmod-simp-dhcp
- pupmod-simp-freeradius
- pupmod-simp-iptables
- pupmod-simp-kibana
- pupmod-simp-libvirt
- pupmod-simp-logrotate
- pupmod-simp-mcafee
- pupmod-simp-mcollective
- pupmod-simp-mozilla
- pupmod-simp-named
- pupmod-simp-network
- pupmod-simp-nfs
- pupmod-simp-nscd
- pupmod-simp-ntpd
- pupmod-simp-oddjob
- pupmod-simp-openldap
- pupmod-simp-openscap
- pupmod-simp-pam
- pupmod-simp-pki
- pupmod-simp-polkit
- pupmod-simp-postfix
- pupmod-simp-pupmod
- pupmod-simp-rsync
- pupmod-simp-rsyslog
- pupmod-simp-selinux
- pupmod-simp-simp
- pupmod-simp-simplib
- pupmod-simp-site
- pupmod-simp-snmpd
- pupmod-simp-ssh
- pupmod-simp-sssd
- pupmod-simp-stunnel
- pupmod-simp-sudo
- pupmod-simp-sudosh
- pupmod-simp-svckill
- pupmod-simp-sysctl
- pupmod-simp-tcpwrappers
- pupmod-simp-tftpboot
- pupmod-simp-tpm
- pupmod-simp-upstart
- pupmod-simp-vnc
- pupmod-simp-vsftpd
- pupmod-simp-windowmanager
- pupmod-simp-xinetd
- pupmod-simp-xwindows


## Unmananged Modules
Some module repositories under the `simp/` org are forks from elsewhere. The SIMP team does not maintain common assets for them:

- augeasproviders
- augeasproviders_apache
- augeasproviders_base
- augeasproviders_core
- augeasproviders_grub
- augeasproviders_mounttab
- augeasproviders_nagios
- augeasproviders_pam
- augeasproviders_postgresql
- augeasproviders_puppet
- augeasproviders_shellvar
- augeasproviders_ssh
- augeasproviders_sysctl
- puppet-datacat
- puppet-elasticsearch
- puppet-gpasswd
- puppetlabs-apache
- puppetlabs-inifile
- puppetlabs-java
- puppetlabs-java_ks
- puppetlabs-mysql
- puppetlabs-postgresql
- puppetlabs-puppetdb
- puppetlabs-stdlib
- puppet-logstash
