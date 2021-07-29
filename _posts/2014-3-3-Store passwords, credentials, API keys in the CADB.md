---
layout: default
title: Store passwords, credentials, API keys in the CADB
---

Updated 07/15

When creating your tree, use the DB patch to store your passwords. Information should be stored in key-value format only. So every entry will have one "key" and one "value; and therefore, for credentials, there will be atleast 2 entries in the DB, whose keys will be of the form "credentials-quaker-username" and "credentials-quaker-password"

**Do not store credentials in your trees**