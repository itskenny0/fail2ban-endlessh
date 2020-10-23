# fail2ban-endlessh

## Intro

I love the idea of [endlessh](https://github.com/skeeto/endlessh), but I want to keep my SSH server running on port 22.
At the same time, I like to waste the time of people with malicious intent.

This led me to write this short config for fail2ban that will, instead of banning the IP that has mistreated you, redirect all its traffic to a locally running instance of endlessh and keep wasting its time.

While this method is not as effective as endlessh itself, it serves as a good middle ground and requires very minor modifications to your system.

## Installing

This tutorial is assuming you are using a systemd-based Debian/Ubuntu/familiars distribution. The principle should be the same for other distros, but the paths might be different.

* Install endlessh on your local machine and have it listen at port 2222 (default) or change the port in `action.d/endlessh.conf`.
* Copy `action.d/endlessh.conf` to `/etc/fail2ban/action.d/endlessh.conf`
* Copy `jail.d/endlessh.conf` to `/etc/fail2ban/jail.d/endlessh.conf`
* Execute `systemctl reload fail2ban.service`

## Credits
* Thanks to Chris Wellons (@skeeto) for [endlessh](https://github.com/skeeto/endlessh) and [his blog post about it](https://nullprogram.com/blog/2019/03/22/)
* Thanks to @notthebee on YouTube for making me aware of endlessh in [his video](https://www.youtube.com/watch?v=SKhKNUo6rJU) about the topic
* Thanks to everyone in [this GitHub issue](https://github.com/fail2ban/fail2ban/issues/419) that got me on the right path
