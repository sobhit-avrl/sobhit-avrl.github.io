---
layout: default
title: Getting the CA to call a local module
---

Updated 07/15


The CA is capable of running modules present locally to the folder of the CA. This is great because the functionality of the CA can be extended on a client-specific basis (but modules can be shared across a certain select set of clients, if they've paid for that module).
The ARPA command to get the CA to run a module is:

<div style="background-color: yellow;padding: 5px;">COMPRUNSCRIPT(\<module_name\>, \<module_params\>, \<wait_for_response:bool\>, \<is_python_script:bool\>, \<python_command\>)</div>

The parameters are:
+ module_name: The name of the module without the "avrlmodule_" prefix
+ module_params: Module params can be sent in two ways depending on how module is accepting it:
    - if module is expecting string (single args ) “USA”, (multiple string args) “USA,CA,MODESTO” 
    - JSON object {“country”:”USA”,”city”:”MODESTO”,”state”:”CA”}
+ wait_for_response: Sometimes ARPA doesn't care about the module providing a response. In these cases, this value could be set to false, allowing ARPA to proceed without waiting for a response
+ is_python_script: The CA needs to differentiate between exe modules and .py modules. This parameter allows it to differentiate and run the module correctly
+ python_command: ----? \<python\>,\<python3\> ,\<python2\>(can be different on different systems)