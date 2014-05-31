Role Name
========

An ansible role to install and configure nullmailer, a sendmail/qmail/etc
replacement MTA for hosts which relay to a fixed set of smart relays.
http://untroubled.org/nullmailer/

Requirements
------------

None.

Role Variables
--------------

nullmailer adminaddr and nullmailer_remotes are the variables that should at 
least be set to have some functional nullmailer.
Other variables have sane defaults, and function mostly like nullmailer would
default.


### nullmailer_adminaddr

default: empty string

If this variable is not empty, all recipients to users at either "localhost" (the
literal string) or the canonical host name (from /etc/mailname) are remapped
to this address. This is provided to allow local daemons to be able to send
email to "somebody@localhost" and have it go somewhere sensible instead of
being bounced by your relay host.


### nullmailer_remotes

default: empty list

This  file contains a list of remote servers to which to send each message.
Each line of this file contains a remote host name or address followed by an
optional protocol string, separated by white space. The protocol name defaults
to smtp, and may be followed by command-line arguments for that module.


### other variables and their default setting

* nullmailer_me:                ansible_fqdn
* nullmailer_defaultdomain:     ansible_domain
* nullmailer_defaulthost:       ansible_fqdn
* nullmailer_helohost:          nullmailer_me
* nullmailer_idhost:            nullmailer_defaulthost
* nullmailer_pausetime:         60
* nullmailer_sendtimout:        3600
* nullmailer_mailname:          nullmailer_me


Dependencies
------------

None

License
-------

GPLv3

Author Information
------------------

Serge van Ginderachter <serge@vanginderachter.be>

