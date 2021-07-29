---
layout: default
title: Approvals Process
---

Updated 7/12



The approvals process is how non-admin users (everyone except Ashwin & Nikolai) build trees and permission access to those or other trees. Non-admin users need to go to the Approvals Requester system at <a href="https://studio.avrlgeneration.com/approvals_requester" target="_blank">https://studio.avrlgeneration.com/approvals_requester</a> to create a new request. These requests can then be downloaded as JSON files for posting in the "approvers" Teams channel. By posting on this channel, you become a requester.

The purpose of this Teams channel is to give everyone global visibility to the permissioning being provided; in an attempt to adopt the "many eyes" approach to spotting something going wrong. However, because the Teams channel can't make sense of the JSON files being created, the requester **must** describe the request in the Teams post. Shorthand my be used, such as:


**treename1 -> treename2** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; _cloning treename1 to treename2_

**new studio user mmstudio**			_creating a new studio user**_

**new tree treename3**				_creating a new tree called treename3_

**new consumer user mmconsumer**		_creating a new consumer user**_

**tree access treename4 mmstudio**		_give access to treename4 to mmstudio**_

_** indicates that you will not need to use this if you're performing actions in the templates account on the Studio. In the templates account:_

- all AVRL team members already have studio & consumer users

- whenever a tree is cloned from another tree inside the studio, all studio users automatically have access to it

Make sure **every single** request JSON is captured in the Teams post.

Important :

a. If you are cloning a tree, **a new destination tree** will be created. Do not pre-create that destination tree. If you do this wrong, the admin will point this out and you will need to create a new JSON request

b. If you have been asked to update your JSON file on a request, post the new JSON in the thread. **Do not replace / delete the existing JSON request**

c. Whether cloning or making a new tree, permissioning for users should come only **after** the clone / create request

d. Starting July 26, 2021 - all approvals shall be processed by an admin only 3 times a day (i.e., 3 cycles). Those times are :

9AM EST / 8AM CST / 4PM EEST

01:50PM EST / 12:50PM CST / 8:50PM EEST

04:50PM EST / 03:50PM CST / 11:50PM EEST

Processing cycles may occur upto 30 minutes before or the above-designated time depending on the availability of the approver.


<div style="background-color: yellow;padding: 5px;">Admins follow an internal rule to indicate which admin is working on a request. If your post has been marked with a thumbs up, it means that the marking administrator is currently working on your request. If your request has been approved, the admin will comment "done" on that post. Do not write back or add additional emojis to a post.</div>



<div style="background-color: cornflowerblue;padding: 5px;">PMs and TDMs: 
Please schedule and perform weekly checks on the whohasaccess system for your designated clients so that you can make the requests for removal of superfluous / unnecessary access to trees by AVRL FDEs. Please schedule this into your calendar.
 
Removal of access should be rare in a well-oiled machine, because ordinarily the FDEs should not have access to trees in a customer's account, unless the tree has come back via Boomerang or needs to be re-worked.
</div>