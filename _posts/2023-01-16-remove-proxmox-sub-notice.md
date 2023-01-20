---
layout: post
author: Angel
date: 2023-01-16
title: Remove Proxmox Subscription Notice
description:
tag: ["homelab", "dell"] 
category: homelab
excerpt_separator: <!--more-->
published: false
---

Every once in a while, I run an update on my proxmox server and reboot. <!--more--> Usually after any major update or reboot, the subscription notice banner reappears on the login screen, which can be a bit distracting.

## Quick

To get rid of the message, open a shell under the root user and type in the snipped below.

```
sed -Ezi.bak "s/(Ext.Msg.show\(\{\s+title: gettext\('No valid sub)/void\(\{ \/\/\1/g" /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js && systemctl restart pveproxy.service
```

## Manual Steps

Here are alternative step by step instructions so you can understand what the above command is doing:

1. Change to working directory

```
cd /usr/share/javascript/proxmox-widget-toolkit
```
2. Make a backup

```
cp proxmoxlib.js proxmoxlib.js.bak
```
3. Edit the file

```
nano proxmoxlib.js
```
4. Locate the following code
(Use ctrl+w in nano and search for “No valid subscription”)

```
Ext.Msg.show({
  title: gettext('No valid subscription'),

```
5. Replace “Ext.Msg.show” with “void”

```
void({ //Ext.Msg.show({
  title: gettext('No valid subscription'),
```
6. Restart the Proxmox web service (also be sure to clear your browser cache, depending on the browser you may need to open a new tab or restart the browser)

```
systemctl restart pveproxy.service
```
## Additional Notes

You can quickly check if the change has been made:
```
grep -n -B 1 'No valid sub' proxmoxlib.js
```
You have three options to revert the changes:

- Manually edit  proxmoxlib.js to undo the changes you made
- Restore the backup file you created from the proxmox-widget-toolkit directory:

```
mv proxmoxlib.js.bak proxmoxlib.js
```
- Reinstall the proxmox-widget-toolkit package from the repository:

```
apt-get install --reinstall proxmox-widget-toolkit
```

[ < back ](/blog)
