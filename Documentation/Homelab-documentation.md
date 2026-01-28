# My HomeLab
this is the documnentation of my homelab, this doc goes over how and why I implemented software on my homelab and it's purpose in my overall system
This document is also here to keep track of the changes I made on my homelab to not lose track of my progress and for me to be able to recreate my system on other machines.  

### Services I want to run on Proxmox:
- Minecraft server 
- Pi-Hole + unbound
- Syncthing: figure out how it works and how to use it
- Reverse proxy
- ansible script to deploy server anywhere
- Prometheus/Grafana for monitoring the system.
- a password manager: vaultwarden (least priority)

## Minecarft Server: PaperMC 
    Initially I had plans to run this server on a VM 24/7 this was to be able to play with my Highschool friends on the same server and stay connected with over long distances. Unfortunaltly as any minecraft, there was no players logging on for long time and running the server 24/7 was a waist of ressources. 
Mainly power was waisted keeping the system on but in my eyes there was cpu ressources that were left unused as the server was running on half my cpu cores.
 I needed a change of plans since it was the first it was an online server running 24/7, it will shift to a server that I can play on and other could join. Since purpose of this VM has shifted so will how it's implemented:
 - remotly turned on/off without ssh or wihout the proxmox UI
 - scheduled up time and downtime
 - automated messages to the in game server 
 - improve plugins to add to the vanilla+ experience.

### remote control via local webpage
    connect to a local webpage that will allowed to type commands in the server and turn it on and off at will

### Scheduled uptime and downtime
    this will take advantage of cron and will run on the main OS where it will boot the VM then log in into the debian server 
 ## Network wide ad-blocking: Pi-hole + unbound 
    Initially I planned on using a network wide ad blocker with a pi-hole: here are my reasons why I went with adGuard home


