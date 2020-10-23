# fail2ban-endlessh

## Intro

I love the idea of endlesssh (https://github.com/skeeto/endlessh), but I want to keep my SSH server running on port 22.
At the same time, I like to waste the time of people with malicious intent.

This led me to write this short config for fail2ban that will, instead of banning the IP that has mistreated you, redirects all its traffic to a locally running instance of endlessh.
While this method is not as effective as endlessh itself, it serves as a good middle ground and requires very minor modifications to your system.

## Installing

This tutorial is assuming you are using a systemd-based Debian/Ubuntu/familiars distribution. The principle should be the same for other distros, but the paths might be different.

* Install endlessh on your local machine and have it listen at port 2222 (default) or change the port in ´action.d/endlessh.conf´.
* Copy ´action.d/endlessh.conf´ to ´/etc/fail2ban/action.d/endlessh.conf´
* Copy ´jail.d/endlessh.conf´ to ´/etc/fail2ban/jail.d/endlessh.conf´
* ´systemctl reload fail2ban.service´

## Credits
* Thanks @skeeto for endlessh
* Thanks to WolfgangsChannel on YouTube for making me aware of endlessh in his video about the topic (https://www.youtube.com/c/WolfgangsChannel)
* Thanks to everyone in this GitHub issue that got me on the right path: https://github.com/fail2ban/fail2ban/issues/419
