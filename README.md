# openscap-centos-8-vagrant

Goal: Use openscap and the security guide on centos 8 to demonstrate compliance failures.

## Bugs

### Workaround for lack of centos 8 in scap-security-guide

The problem is that the scap-security-guide rpm does not include centos 8 in its built-in cpe platform identifiers:

```
[vagrant@localhost ~]$ oscap --version | egrep 'Inbuilt CPE names|:/o:(centos|redhat):'
==== Inbuilt CPE names ====
Red Hat Enterprise Linux - cpe:/o:redhat:enterprise_linux
Red Hat Enterprise Linux 5 - cpe:/o:redhat:enterprise_linux:5
Red Hat Enterprise Linux 6 - cpe:/o:redhat:enterprise_linux:6
Red Hat Enterprise Linux 7 - cpe:/o:redhat:enterprise_linux:7
Red Hat Enterprise Linux 8 - cpe:/o:redhat:enterprise_linux:8
Community Enterprise Operating System 5 - cpe:/o:centos:centos:5
Community Enterprise Operating System 6 - cpe:/o:centos:centos:6
Community Enterprise Operating System 7 - cpe:/o:centos:centos:7
[vagrant@localhost ~]$ rpm -q openscap scap-security-guide
openscap-1.3.1-1.el8.x86_64
scap-security-guide-0.1.46-1.el8.noarch
[vagrant@localhost ~]$ rpm -q scap-security-guide -l | grep -e -ds\\.xml
/usr/share/xml/scap/ssg/content/ssg-firefox-ds.xml
/usr/share/xml/scap/ssg/content/ssg-jre-ds.xml
/usr/share/xml/scap/ssg/content/ssg-rhel6-ds.xml
/usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml
/usr/share/xml/scap/ssg/content/ssg-rhel8-ds.xml
[vagrant@localhost ~]$
```

Using the `--cpe` option to specify the dictionary ... TODO ...

Other ideas:

Copy /usr/share/xml/scap/ssg/content/ssg-rhel?-ds.xml to /home/vagrant/ssg-centos?.xml, replacing "cpe:/o:redhat:enterprise_linux:?" with "cpe:/o:centos:centos:?"

Possible replacement RPM? https://copr.fedorainfracloud.org/coprs/openscapmaint/openscap-latest/

Someone with the same problem https://forums.centos.org/viewtopic.php?t=72271
