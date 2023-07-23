FOG Project 1.5.9+ with FOGUefi && PDS Scripts - Free and Open-source Ghost (MOD)  
=================================================================================

**This is the recipe for FAB (included in TKLDEV Turnkey DEV Environment)**

`FOG Project`_ The FOG Project is a software project 
that implements FOG (Free and Open-source Ghost), 
a software tool that can deploy disk images of 
Microsoft Windows and Linux using the Preboot 
Execution Environment. It makes use of TFTP, 
the Apache webserver and iPXE.
It is written in PHP.

The configuration tool developed by the FOG Project 
makes it possible to do remote system administration 
of the computers in a network. 
FOG depends on Partclone to copy the disk image. 

This appliance includes all the standard features in `TurnKey Core`_,
and on top of that:

- FOG Project configurations:
   
- Installed from upstream source code to /var/www/fog

**Security note**: Updates to FOG Project may require supervision so
they **ARE NOT** configured to install automatically. See `FOG
Project documentation`_ for upgrading.

- SSL support out of the box.
- `Adminer`_ administration frontend for MySQL (listening on port
  12322 - uses SSL).
- Postfix MTA (bound to localhost) to allow sending of email (e.g.,
  password recovery).
- Webmin modules for configuring Apache2, PHP, MySQL and Postfix.

*Plugins* are activated by default in FOG Web interface.

PostDownloadScript is a pre-installed plugin, which allows to execute scripts according to deployed images. This allows deploying driver packages before the system boots.

An addition "foguefi" makes it possible to boot network FOG without having to deactivate Secure Boot.
For this, you must changes into your DHCP server, the option 67 (Boot file) to shimx64.efi

Credentials *(passwords set at first boot)*
-------------------------------------------

-  Webmin, SSH, MySQL: username **root**
-  Adminer: username **adminer**
-  FOG: username **fog**

Notes
-----

-  If you change the IP address of your server, you *must* choose "Change IP address" and "Regen certificates" into confconsole, else FOG dosent work properly.

.. _FOG Project: https://fogproject.org/ 
.. _TurnKey Core: https://www.turnkeylinux.org/core 
.. _Adminer: https://www.adminer.org 
.. _FOG Project documentation: https://docs.fogproject.org/en/latest/installation/install_fog_server.html#install-fog-server

