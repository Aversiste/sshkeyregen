sshkeyregen
===========

Introduction
------------

This is a LSB compliant init script I use on my Debian XEN templates. I haven't
tested it on other hypervisor nor other operating systems, so be careful if you
plan to use it on another plateform.

Sshkeyregen will try to create SSH host keys at startup, both RSA, DSA and ECDSA
 if supported.

After the first boot the script will remove itself from the active init script, but the file will still exist in /etc/init.d/.

You can force the re-creation of keys with `/etc/init.d/sshkeyregen restart`.

Installation
------------

    find /etc/ssh/ -name 'ssh_host_*' -exec rm {} \;
    cp sshkeyregen /etc/init.d/
    chown +x /etc/init.d/sshkeyregen
    update-rc.d sshkeyregen defaults

Support
-------

   * Debian squeeze

License
-------

Sshkeyregen is under ISC license.

