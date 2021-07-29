---
layout: default
title: Storing User Settings for the ARPA bot for the CADB's storage
---

Updated 07/15

Storing settings for the ARPA bot (i.e., whether to bid on reefer, etc.) is encouraged if that setting doesn't change often (less than once in 12 months). Otherwise, this data needs to be stored in the tree.
Name the key as setting-<<setting name>>; valid examples:

**setting-premium-reefer**

**setting-is-unattended**

When storing bid information DO NOT store data in a key that will grow the next day.
i.e. so storing data for a bidboard called tender should be with a key in the format of :
info-<tree-name or board-name>-<date>. This will ensure that the key for that date finds the information relevant to that date.

_We tested and found that 50,000 DB entries resulted in a 250MB DB size, which is small enough to allow us to neglect having to "clean" up old entries. However, if old entries need to be cleaned up, all entries to the CADB are auto-inserted with a column that contains UTC insertion date-time entry to allow easy deletion of older entries_.
_Important_: _The column name for this date-time entry is created_ _ _at so you can access that information if needed from ARPA itself to determine when this data was inserted_.