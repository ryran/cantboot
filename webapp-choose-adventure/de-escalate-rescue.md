<!DOCTYPE html>
<html>
<title>Can't-boot First-Responders: De-escalate - Rescue mode</title>
<xmp theme="united" style="display:none;">

### De-escalation work-around #2 - Use rescue mode to bring up system

Resources:

- [RHEL 7 Installation Guide - Basic System Recovery](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/Installation_Guide/chap-basic-system-recovery.html)
- [RHEL 6 Installation Guide - Basic System Recovery](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Installation_Guide/ap-rescuemode.html)
- [RHEL 5 Deployment Guide - Basic System Recovery](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/5/html/Installation_Guide/ch-rescuemode.html)

Steps:

1. Boot system into rescue mode using the DVD iso which is the latest minor version of the major version customer is using (e.g., if customer reports system is RHEL 5.5, use 5.11 DVD)

1. When prompted, don't bother enabling networking (you can do it later)

1. When prompted, have rescue mode attempt to autodetect and mount everything
  
1. Chroot into OS root filesystem

1. Bring up networking and potentially any other of the customer's production services, e.g.:
  - `service network start`
  - `service sshd start`
  - `service httpd start`

1. Result:
  - [The customer was able to access needed production services from another machine!](congrats.html)
  - [Things didn't go smoothly and this wasn't good enough!](de-escalate-rescue2.html)

</xmp>
<script src="http://strapdownjs.com/v/0.2/strapdown.js"></script>
</html>
