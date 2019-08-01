https://research.cs.wisc.edu/htcondor/instructions/el/7/stable/

##Common
```
wget http://research.cs.wisc.edu/htcondor/yum/repo.d/htcondor-stable-rhel7.repo
```
#should be in /etc/yum.quattor.repos.d/
#
```
wget http://research.cs.wisc.edu/htcondor/yum/RPM-GPG-KEY-HTCondor
rpm --import RPM-GPG-KEY-HTCondor
```
#add condor-* to /etc/yum.quattor.d/epel-7-x86_64.repo or adjust priority
```
yum install condor
```


#condor

#CE
#https://htcondor-wiki.cs.wisc.edu/index.cgi/wiki?p=InstallHtcondorCe
```
yum install htcondor-ce-condor
yum install fetch-crl
systemctl enable fetch-crl-boot
systemctl enable fetch-crl-cron
systemctl enable condor
systemctl enable condor-ce
systemctl start fetch-crl-boot
systemctl start fetch-crl-cron
systemctl start condor
systemctl start condor-ce
condor_ce_on
```

#Check CE is working
http://indico4.twgrid.org/indico/event/8/session/0/contribution/159/material/slides/0.pdf
```
condor_ce_host_network_check
condor_ce_status -any
condor_ce_trace --debug host-172-16-113-218.nubes.stfc.ac.uk:9618
```

