---
layout: default
title: Variable Names
---

Conventions ( Variable Names )


+ Variable names need to be lowercase and contain underscores to separate tokens
    Valid: $client_id, $distance
    _Invalid_ : _$ORIGIN_ , _$Destination_ _ _Id_

+ Variables should be used across all nodes as though they are in global scope
    This means that:
    - do not reuse a variable name for a different purpose

e.g., the index variable for generated bid & refill bid shouldn't have the same name

Valid: $generate_bid_row_index, $refill_bid_row_index

_Invalid_: _$index_ _(used for generate and refill)_
