---
layout: default
title: Setting up the CA
---

Updated on 07/15


Here are the steps for setting up a CA on a new PC or VM. 
**Before the HO call:**
+ PM/TDM to create a consumer account for the CA and this request to be sent to approvers channel
    - Consumer User Name:
    Format: uaconsumer<identifier> 
    identifier is any way to describe this VM, i.e., warehouse1. **NO SPACES**

    eg: uaconsumerwarehouse1
    - Consumer Full Name:
    Format: Unattended Consumer <identifier> 
    eg: Unattended Consumer Warehouse Black PC

    - Consumer User Email ID: <u>ashwin@avrl.io </u>

    - Consumer User Group: default

    - Reason: For setting up UA process on _________

+ Engineering to configure this file generation_companion_config.json for:

    For Automated 

    1. client_name
    2. username
    3. password
    4. scheduler_id
    5. error_webhook
    6. gui_error_messsage
    7. minutes (5 mins intervals)
    8. scheduler_tree
    9. Format: <client_name>_lb_<prod/dev/test>_scheduler_vX

+ Create a client specific folder on GCS in (<a href="https://console.cloud.google.com/storage/browser/customer_facing_downloads/arpa_companion_app?project=avrlgeneration&pageState=(%22StorageObjectListTable%22:(%22f%22:%22%255B%255D%22))&prefix=&forceOnObjectsSortingFiltering=false" target="_blank">https://console.cloud.google.com/storage/browser/customer_facing_downloads/arpa_companion_app?project=avrlgeneration&pageState=(%22StorageObjectListTable%22:(%22f%22:%22%255B%255D%22))&prefix=&forceOnObjectsSortingFiltering=false</a>) and add :

    - Config file previously created
    - logdb
    - Any additional files that are needed


+ Setup and Test Scheduler tree with the scheduler_id configured in step 2.


**During / On the HO call:**

1. Follow this step (step 1) **only if** the CA has not been installed on this PC before :

    - Download the installer from <a href="https://storage.googleapis.com/misc_demo_staging_dr/generation_companion/installer_generation_companion.exe" target="_blank">https://storage.googleapis.com/misc_demo_staging_dr/generation_companion/installer_generation_companion.exe</a> 

        **[ Link updated on 07/22, update to 003122072021]**

    - Double click on the exe after downloading

    <span style="color:red">Warning: If the install script is run a second time, any existing config file will be overwritten.</span>

    - It will prompt with a blue dialog box

    ![an image alt text]({{ site.baseurl }}/images/installing_1.png "an image title")

    Click on More Info.

    ![an image alt text]({{ site.baseurl }}/images/installing_2.png "an image title")

    Click on Run Anyway

    A command line window will appear

    ![an image alt text]({{ site.baseurl }}/images/installing_3.png "an image title")

2. Navigate to C:\Users\<logged-user-name>\AVRL Generation\Generation Companion to check if the application is installed.

3. Download the client-specific folder.
    https://storage.googleapis.com/customer_facing_downloads/arpa_companion_app/<client_name>/<random-filename>/<account name>/<filename>.zip

    Replace the config file present in the Companion App folder. Retrieve this config file from the link above in #3; place in C:\Users\<logged-user-name>\AVRL Generation\Generation Companion\

4. Double click on generation_companion.exe to check if the configuration file is correct.

    ![an image alt text]({{ site.baseurl }}/images/installing_4.png "an image title")

    Vikash will debug any issues.

    Expected issue:
    - Credentials are not correctly copied
    - The Scheduler Tree is missing or incorrect. 


5. Check is desktop shortcut is working

    ![an image alt text]({{ site.baseurl }}/images/installing_5.png "an image title")

    This link should be visible on desktop

6. Check if the startup link is working correctly.

    - In cmd line type: shell:starup

        ![an image alt text]({{ site.baseurl }}/images/installing_6.png "an image title")

    - You should see a shortcut link in the folder opened

        ![an image alt text]({{ site.baseurl }}/images/installing_7.png "an image title")



**CA installation for Augmented Bots**

1. Install CA app via installer

2. Download [CSV file, CA modules]  from client_specific_folder. (<a>https://storage.googleapis.com/customer_facing_downloads/arpa_companion_app/...</a>)

    Need to be created before the HO call.

3. Transfer data.csv into C:\Users\<windows-username>\AVRL Generation\Generation Companion\patch

4. Run db-patch.exe

    - Enter 1 and press enter.( Your choice)

        ![an image alt text]({{ site.baseurl }}/images/installing_8.png "an image title")

    - Enter y and press enter  to update credentials. ( Confirm loading)

        ![an image alt text]({{ site.baseurl }}/images/installing_9.png "an image title")


5. Update generation_companion_config.json with consumer details 

    - client_name
    - username
    - password

    Save the file. 

6. Run Companion App

7. Then proceed to install ARPA Bot Chrome extension


