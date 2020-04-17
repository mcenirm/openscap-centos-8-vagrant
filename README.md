# openscap-centos-8-vagrant

Goal: Use openscap and the security guide on centos 8 to demonstrate compliance failures.

## Bugs

### Workaround for lack of centos in scap-security-guide

Copy /usr/share/xml/scap/ssg/content/ssg-rhel?-ds.xml to /home/vagrant/ssg-centos?.xml, replacing "cpe:/o:redhat:enterprise_linux:?" with "cpe:/o:centos:centos:?"

Possible replacement RPM? https://copr.fedorainfracloud.org/coprs/openscapmaint/openscap-latest/

Someone with the same problem https://forums.centos.org/viewtopic.php?t=72271
