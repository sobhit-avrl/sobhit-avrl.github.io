---
layout: default
title: Creation & Access to Trees
---

Updated 07/22


This new structure means that all trees will be created (including existing trees) inside the **templates** account itself. For managers, please follow this process:

+ Creation of a new RPA (chatbot) tree should follow standard nomenclature and should be inside the **templates** account **only**.

+ The same applies for analytics trees

+ Use the templates global JSON file to provide global access when an RPA template for a board is created (Don't wait until the FDE has finished configuring it)

**Creating New Trees to Upgrade Existing Trees**

_This is applicable only when upgrading an existing tree (i.e., the same TMS & same account). This is not the approach when cloning a tree from an existing account to a new account_.

Under the old standard, if a client wanted to update / improve an existing tree, they would ask for a v2 or v3 "version" of their tree. This was so that the existing tree could continue to serve the bot while the new tree was "improved" without breaking the existing bot. However, this led to multiple trees with different version numbers and sometimes confusion about which tree was most recent.

Now, instead of creating trees with different version numbers, we have a different approach.

+ The client or the internal user identifies the tree they want to upgrade

+ The tree is cloned within the same account to a tree named sandbox_<tree purpose>{_option2}

+ The client or internal user makes changes to that tree

+ The changes are made to the tree

+ The sandbox tree is then cloned back to the original tree