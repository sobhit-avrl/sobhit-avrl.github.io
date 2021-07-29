---
layout: default
title: Unattended Bots
---

Updated 07/15


+ **Correct shut down after bot execution is completed**

    When a bot is run unattended on a VM, the CA automatically opens up the Chrome window to run a bot. When the bot is done, the correct behavior would be to have the tree instructions tell the ARPA Chrome Extension to shut down any Chrome tabs. The ARPA command you should use in the tree is:
    close_unattended_tabs()

+ **Issues with the bot not running / Incorrect disconnect from VM**

    Only VMs with a desktop / window manager can be used for unattended operations. This is because although Chrome is able to start in a non-windowed environment, it actively prevents Chrome Extensions from running.
    To complicate things, even VMs with windowed capabilities **normally** shut down their window manager when a user disconnects through a normal RDP disconnect. This is because the VM is trying to save processing power (which window managers hog). As a result of the normal disconnect, the following may occur:

    - a user logs into the VM, then disconnects (resulting in the window manager being killed)

    - on time, the ARPA CA runs, checks the scheduler tree, finds it has a bot to run and kicks off Chrome and tries to run the ARPA Chrome Extension

    - However, the ARPA Chrome Extension cannot run, so there is just a Chrome window open, but no bot running. And because there is no bot running, there is no way to close Chrome.
    
    - <span style="color:red">_Because there is no way to close Chrome, everytime the CA runs on schedule and tries to fire up a bot, no bot is actually started and the end result is there are hundreds of new Chrome windows opened up in a short span of time_</span>