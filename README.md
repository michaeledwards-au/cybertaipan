# Checklist for Cyber-Taipan Competition

## Notes

When going through the README file on the image, think about all the tasks that could exist for each sentence.

Jot them down and at the end, assign a amount of time to each task, then group into hours so at each hour if you are stuck move onto the next hours' tasks.

Most things can be done from the Terminal (press the Windows key, and search for Terminal to open it), and you should be able to find a command to do what you need.

**If you don't understand a word or term, Google it. Also, if you are unsure how to do something Google `'ubuntu [version] [thing you want to do]'`.**

## Overview

1. [Read readme file](#read-readme-file)
2. [Enter team ID](#enter-team-id)
3. [Open a root terminal](#open-a-root-terminal)
4. Do forensic questions
5. Check users
6. Check passwords
7. Check files
8. Do updates
9. Check software
10. Secure the network
11. 

## Read readme file

**MAKE SURE TO DO THIS FIRST**

Make notes of tasks for each sentence in the readme file.

Note down users, if they are administrators or standard users, and what their passwords are.

Note down any PORTS that need to be open/closed.

## Enter team ID

Enter your team ID in otherwise the VM might lockdown.

Coach should have the team ID emailed day of.

## Open a root terminal

[open-a-root-terminal.webm](https://github.com/michael3dwards/cybertaipan/assets/29730059/d1310e7d-0633-446b-82da-1606bfecb074)

Open Terminal by pressing CTRL+ALT+T on the keyboard, or by clicking the app button on the dock on the left, and searching for Terminal and clicking on it.

An icon will appear for it on dock that looks like a black console window, right click and select 'add to favourites' in case you close it, you just need to click this icon to open it again.

In the terminal, note the username (left of the @ symbol). You will need to look up the password for this user from the readme file.

Type `sudo su` and press Enter on the keyboard. You will be asked for the user's password. Type this in a press Enter on the keyboard.

This will make you the "root" user which will allow you to do anything to config the system. It saves you typing `sudo` in front of everything command

## Do forensic questions

**The forensic questions are located on the desktop and need to be attempted first!**

If other parts are done, it may mess up the answers you need to get.

## Check users

### Disable guest account


Go to /etc/lightdm/lightdm.conf and add the line

allow-guest=false

Then restart your session with sudo restart lightdm. This will log you out, so make sure you are not executing anything important.

### Secure root login through openssh

[secure-root.webm](https://github.com/michael3dwards/cybertaipan/assets/29730059/699efb87-4e5e-4ac1-bef7-ec029bec3dea)

### Remove users not in readme file

[list-and-remove-users.webm](https://github.com/michael3dwards/cybertaipan/assets/29730059/dc0a3b07-8e66-49d7-9104-e6942eee4c04)

Go into the ubuntu apps but clicking the app button on the dock.

Types in `users` and click on the users entry.

Click the unlock button and type in the user password to unlock the users screen.

Remove any users that should be there. Not any users that are missing.

### Add users that are needed to be there

[add-user.webm](https://github.com/michael3dwards/cybertaipan/assets/29730059/430a3be4-3152-4da2-b11c-26143fd9f63b)

In terminal (with root) type:

`adduser <user>`

`<user>` is the name of the user. Usernames are CASE-SENSITIVE!

Set password as per the readme, if no password specified, make sure it meets minimum requirements.

If the user needs administrator privileges, add them to the `sudo` group by typing:

`usermod -aG sudo <user>`

`<user>` is the name of the user. If they need to be part of another group replace `sudo` with group.

## Check passwords

### Change passwords

[change-passwords.webm](https://github.com/michael3dwards/cybertaipan/assets/29730059/124a8e60-5f65-40d7-8ccb-7c737c4fcf7f)

Open users and change all passwords to `Cyb3rT@!pan2023`.

Make sure this doesn't violate rules in the readme. ie, you might be required to create a user with a particular password.

The point of this is to make all the passwords strong.

**REMEMBER: IF YOU CHANGE THE CURRENT USER THE ABOVE PASSWORD WITH BE YOUR NEW SUDO PASSWORD**

## Check files/programs

## Do updates

### Update all the software to the latest version

In terminal (as root) type:

`apt update; apt -y upgrade`

This may take a little while.

## Check software

## Secure the network

### Activate firewall

[activate-firewall.webm](https://github.com/michael3dwards/cybertaipan/assets/29730059/f64f4d1b-d868-45d1-b321-93cba34b94b9)

In the terminal (as root) type:

`apt install -y ufw; ufw enable`
