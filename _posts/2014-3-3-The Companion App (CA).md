---
layout: default
title: The Companion App (CA)
---

Updated 07/15


The Companion App has a wide range of functionality
 - **Scheduling Bots to Run**

    The CA checks it's local config file to see at what specific minutes it should reach out the ARPA scheduler tree to see what bots it should run. If there is a match on the scheduler tree, it opens up Chrome
    When the bot is complete, the tree should have a command that makes the Chrome Extension close itself.
 - **Receiving Instructions from Bots to run certain modules**

    Although Generation ARPA has a lot of power, it's privileges are greatly restricted by Chrome in the interests of user safety. To allow ARPA to do new & interesting things, such as taking screenshots, etc, the CA allows us to add python applications to the CA root folder and then to call those python applications from the ARPA tree. The process flow is:
    ARPA Tree → ARPA ChromeExt → ARPA CA → module to run
    These are built as modules to give only specific clients access to only specific functionality. One such functionality is a DB connector that connects the Companion App to the client's SQL DB.
 - **Reading & Writing information to the ARPA Companion App DB**

    To ensure that login credentials and other secret data is stored inside the client network, storage of credentials should never be on the tree (as trees are stored on GCP). They should only be stored on the CADB. There is other information too (such as personalized user preferences, wherein a bot can read user variables from the CADB to change its behavior, like Google Ads' web cookies that influence what ads you see).

    The standard behavior of the CADB is to default to the usage of it's primary table "generalkv". This table has 4 columns: 

    primary key: pk VARCHAR(255) 

    deprecated, naive value: val

    json_value: jval JSON(5000)

    when the insert happened: created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP

 - **Finding matching primary keys using wildcards**

    Queries to the ARPA CADB can search for values from the table using wildcards. An example of a command that should be put into the ARPA tree to find all matching trees for this dataset is:

    | key      | value |
    | :---        |    :----   |
    | person-vikash      | 11       |
    | person-victoria   | 12        | 
    | city-hyderabad      | 14       |
    | town-whitby   | 15        | 

    The syntax for this is companion_db_get_with_wildcard('<wildcard>') and an example of this is companion_db_get_with_wildcard('person-v%') which would yield a result of a NON-JSON list:
    [{ "person-vikash" : 11}, {"person-victoria": 12} ]

    <span style="color:red">In case of failure to retrieve this data, this function will return a generic string "failed". These failures could range from DB unavailability to other unanticipated failures.
    This failure does not include cases where there are no matching results. No matching results will yield an empty list.</span>

    Matching values in other columns is also possible using the API call method. For more on this method, AVRL team should reach out to Vikash Ranjan; and non-AVRL employees should reach out to their Project Manager.

    ![an image alt text]({{ site.baseurl }}/images/ca_one.png "Wildcards in SQL 1")

    ![an image alt text]({{ site.baseurl }}/images/ca_two.png "Wildcards in SQL 2")



