---
layout: default
title: Tree Names
---

Updated 07/16

Tree names are composed of multiple sections, and are prepended with "demo_". Demo trees are never to be used live and are for limited internal demos. Tree naming structure must follow this rule :

bidboards chatbot : **<lb/ta>\_\<tms\>\_\<accountname\>{_<option2/3/4>}>}**

bnb analytics : **<lb/ta>\_\<tms\>\_\<accountname\>\_bnb\_\<customer\>**

pa analytics: **<lb/ta>\_\<tms\>\_\<accountname\>{_<option2/3/4>}>}\_pa\_\<customer\>**

auto accept tender acceptance analytics : **<lb/ta>\_\<tms\>\_\<accountname\>{_<option2/3/4>}>}\_autoaccept\_\<customer\>**

Examples: 
+ lb_mg_dicksonfurniture ( ARPA/Chatbot)
+ lb_mg_dicksonfurniture_bnb_jbhunt  (Bid / No bid for the above lb tree for jbhunt)
+ lb_mg_dicksonfurniture_pa (Pricing augmentation)

Keys:







| Syntax      | Description | Test Text     |
| :---        |    :----   |          :--- |
| Ib/ta     | Ib | Loadboard     |
| Tree Purpose   | ta <br> apiglue        | Tender Acceptance <br> API glue      |
| tms <br> TMS OEM | mg <br> bj <br> ns <br> jda <br> manh <br> oracle <br> hs <br> us <br> fv <br> gocloud <br> ratelinx <br> tp <br> transporeon <br> pbs <br> costco <br> niagara <br> cp | Mercury Gate <br> Blujay <br> Navisphere <br> JDA <br> Manhattan <br> Oracle <br> Haversack <br> Ultraship <br> FreightView <br> Gocloud <br> Ratelinx <br> Transplace <br> Transporeon <br> Postbidship <br> Costco <br> Niagara <br> Carrier Point |