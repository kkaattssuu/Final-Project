# Blue Team SOC Lab

Final project for my Code Academy blue team course, done together with two teammates — Polad and Shamil.

We built two environments: one on AWS (cloud), one running locally (on-prem), and connected them into one SOC setup.

## What we did

**Cloud side (AWS)**

Set up 3 VMs: Web, SOC, Gateway. Locked down SSH to our own IP only. Ran WordPress in Docker behind an Nginx + ModSecurity gateway. Tested the WAF with a basic SQLi payload — got blocked and logged correctly. Installed Wazuh across the servers for monitoring. Wrote custom rules for brute force, SQLi, XSS, WordPress attacks. Hooked up VirusTotal and AbuseIPDB for threat intel. Set up TheHive + Cortex for case management, with Slack/email/Telegram alerts.

**On-prem side (local)**

Set up Palo Alto with zones for Clients, Servers, PAM, WAN. Joined machines to Active Directory, used User-ID to tie policies to users. Applied GPOs — USB blocking, password policy, screen lock, etc. Set up DoS/port scan detection on the firewall. Sent logs to Splunk over syslog. Set up PAM with LDAP, session recording through Guacamole. Fed Palo Alto logs into Wazuh too, so everything lands in one place.

## Tools used
Wazuh, Palo Alto, TheHive, Cortex, Splunk, Docker, Nginx/ModSecurity, Active Directory, PAM, Guacamole
