---
layout: default
title: Working with Existing Tree Templates
---

Updated 15/7

Ideally, existing trees should have only 2 points of modification:
+ Pricing data being fetched from the client's pricing API
+ Data being sent to the client's datastore

Ordinarily, when you start working with an existing template, you will almost always find that you are seeing someone else's code and someone else's variables and a process for some other client (not the one you intend to build this tree out for). 
 
Don't let that change the fact that you should find yourself modifying only the above 2 parts (a) & (b). 
 
This also serves to emphasize that TMS or other credentials should never be stored on the tree themselves, but should be stored on the Companion App DB. This allows trees to be portable.

Some clients have slightly modified the process, e.g. Arcbest doesn't have the ARPA bot call the BidNoBid tree, instead, their pricing API calls the BidNoBid tree and the ARPA bot **only** calls their pricing API.

In this case, we recommend keeping the existing tree structure, but adding an additional branch that either short circuits the existing excess operations or adds more operations (if needed). The following diagram illustrates such an example:


![an image alt text]({{ site.baseurl }}/images/working_with_existing_templates.png "working_with_existing_templates")

In this example, Client1 had required the 2 unique steps (nodes 1003 and 1005, marked in red) for Template1. Those 2 steps were built by the first FDE who built the board. However, when Client2 wanted to use the same template, the FDE found that steps 1003 & 1005 were unnecessary for Client2 (even though they were required by Client1!). Rather than deleting those "extra" nodes, the FDE marks the arrow from 1001 -> 1003 as false and uses a redirect arrow to circumvent the nodes 1003 & 1005. 

The cool thing about this is that if the next FDE is using Template1 for Client3; and they determine that nodes 1003 and 1005 are required, they can convert that 1001->1007 redirect arrow to "false" and re-enable that arrow from 1001 -> 1003.
