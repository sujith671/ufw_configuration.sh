What is UFW?
UFW, or uncomplicated firewall, is a frontend for managing firewall rules in Arch Linux, Debian, or Ubuntu. UFW is used through the command line (although it has GUIs available), and aims to make firewall configuration easy (or, uncomplicated).

{{< note >}} If you are running Docker, by default Docker directly manipulates iptables. Any UFW rules that you specify do not apply to Docker containers. {{< /note >}}
Before You Begin
Familiarize yourself with our Getting Started guide and complete the steps for setting your Linode's hostname and timezone.

Ensure that you complete the sections of Setting Up and Securing a Compute Instance guide to create a standard user account, harden SSH access and remove unnecessary network services. When you reach the Configure a Firewall section return to this guide.

This guide lists the commands for Arch Linux, Debian or Ubuntu distributions only. However, you can use the relevant commands for the outlined tasks on various Linux distributions.

Update your system.

Arch Linux

sudo pacman -Syu
Debian / Ubuntu

sudo apt-get update && sudo apt-get upgrade
Install UFW
Debian starts UFW's systemd unit automatically and enables it to start on reboots, but Arch does not. This is not the same as telling UFW to enable the firewall rules. Enabling UFW with systemd or upstart only tells the init system to switch on the UFW daemon.

By default, UFW's rulesets are blank so it is not enforcing any firewall rules--even when the daemon is running. Enforcing your firewall ruleset is covered further down the page.

Arch Linux
Install UFW:

sudo pacman -S ufw
Start and enable UFW's systemd unit:

sudo systemctl start ufw
sudo systemctl enable ufw
Debian / Ubuntu
Install UFW

sudo apt-get install ufw
