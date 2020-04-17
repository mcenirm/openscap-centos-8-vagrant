# openscap-centos-8-vagrant

Goal: Use openscap and the security guide on centos 8 to demonstrate compliance failures.

## TODO: Figure out how to get a profile that applies to centos 8

Possible replacement RPM? https://copr.fedorainfracloud.org/coprs/openscapmaint/openscap-latest/

Someone with the same problem https://forums.centos.org/viewtopic.php?t=72271

Copy /usr/share/xml/scap/ssg/content/ssg-rhel8-ds.xml to ssg-centos8.xml, replacing "cpe:/o:redhat:enterprise_linux:8" with "cpe:/o:centos:centos:8" ?
