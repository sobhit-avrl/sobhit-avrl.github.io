---
layout: default
title: ARPA Tree Commands for Reading  Writing to the CADB
---

Updated 07/15



+ Important: All values are stored as string, so:

    - it is important to convert to the right type before using
    - you can store JSON objects in the value field. Make sure they're converted to JSON before writing and converted back into objects after reading

+ Writing Example: writing **setting-name1** with a value of **hello world**
    <span style="color: green">companion_db_set('setting-name1', 'hello world', true)</span>
    <span style="color: green">companion_db_set('setting-system-info', {"double":2, "triple":3}, true}</span>
    which is of syntax **companion_db_set(key_name, data_value, whether_overwrite_previous_entry_with_same_key)**

+ Example: reading **setting-name1** into a variable in the tree named **db-name1**
    <span style="color: green">companion_db_get('setting-name1')</span> which is of syntax companion_db_get(key_name)
    The output of this function will be a NON-JSON object i.e., what was initially set in the DB. So if you set a dict-type object, the output of that function will be that dict-type object. If you set a string, the output of that function will be a string.
    <span style="color: red">In case of failure to retrieve a result, the read function (companion_db_get()) will return a generic string "failed". These failures could range from DB unavailability to other unanticipated failures.
    This failure does not include cases where there are no matching results. No matching results will yield an empty list. </span>


