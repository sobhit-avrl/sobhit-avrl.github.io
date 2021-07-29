---
layout: default
title: Bot Prompts
---

Updated 07/15



Please use the following prompts and button texts when prepping a bot:
+ Button Text

    Augmented
    1. Generate Bids
    2. Refresh Page
    3. Re-fill Bids from Cache
    4. Review Data

    _Submit Bid ( After the user clicks on "Go/Submit" button)_
    5. Submit Bid
    6. Do not submit bid
    
    _Account Specific_
    7. Generate Quick Bids [Generate bids recommendation, for bid that timeout within next x mins, Transplace/ Navisphere ]
    8. Record Data [Horizon only]

    _Load Board Specific  [JDA]_
    9. Submit Bids
    10. Decline Bids
    11. Go to Next Page
    12. Go to Previous Page
    13. Load More

    Automated
    1. Generate Bids
    2. Refresh Page
    3. Review Data


+ Prompts
    1. **No Data Present**

        - No data present on loadboard
            Note: Next node to be called is "Refresh Page" 

    2. **Generate Bids**

        Note: All augmented information should be cleared
        - Generate Bids process started <br><p style="color:red">(Do not click on "Generate Bids" process until the process is completed.)</p>
        - Processing load id $load_id
        - $load_id_text: Process bid decision

        If Bid is a no go ( $make_bid == false) 
        - $load_id_text: Bid Failed, $bid_failure_reason
        - $load_id_text: Bid Failed, Weight > 45000
        - $load_id_text: Bid Failed, Lead time < 24 hrs
        - $load_id_text: Bid Failed, Origin city $origin_name 
        - $load_id_text: Bid Failed, Destination city $destination_name
        - $load_id_text: Bid Failed, Origin state $origin_state
        - $load_id_text: Bid Failed, Destination state $destionation_state
        - $load_id_text: Bid Failed, Equipment Type $equipment_type
        - $load_id_text: Bid Failed, Country is CA

        If Rate is returned
        - $load_id_text: $ $bid_submitted recommended rate.

        If Rate returns an error
        - $load_id_text: Pricing Failed, $bid_failure_reason ( extracted from Pricing API error message)

    3. **Refill Bids**

        Note: All augmented information should be cleared
        - Refilling Bids process started <br><p style="color:red">(Do not click on "Refill Bids" process until the process is completed.)</p>
        If all bids are populated

        - All bids populated
        If not all bids are populated (List all load_id will failed to refill) 

        - <span style="color:red">Load ID: "+$load_id+", data not found."</span>

    4. **Submit Bids**

        $load_id: Bid Submitted for $ xxxxx.xx

+ Sending Load information to Teams

    Should only be sent via Teams Cards format.
    Success:[ Blue Line ]

    ![an image alt text]({{ site.baseurl }}/images/prompt_success.png "prompt success")

    Failure: [ Red line ]

    ![an image alt text]({{ site.baseurl }}/images/prompt_failure.png "prompt failure")


    **Title: \<Account Name\> , Quote #\<load-id/shipment-id\>**

	Company Name: <origin-company-name> ( If present on loadboard)

    Pickup:   <orig-city>, <orig-state> -  <orig-postal-code> <orig-country>

    Pickup Date/Time: <origin-datetime> (Value from loadboard not formatted)

	Drop:   <dest-city>, <dest-state>  - <dest-postal-code> <dest-country>

	Drop Date/Time: <origin-datetime> (Value from loadboard not formatted)

	Equipment Type: <equipment-type-text>(from loadboar) ( <equipment-type-code> from analytics tree)

	Distance: <distance_text> ( from loadboard )

	Weight: <weight_text> ( from loadboard )

	Stops: <stop_text> ( from loadboard )

    Bid Datetime : <current-time> ( calculated)

	Make Bid: <make-bid> (from analytics tree)

	Bid Failure Reason: <bid-failure-reason> (from analytics tree)

	Recommended Amount: <recommended-amount> (calculated)

	[Pricing Augmentation Information]

	Additional Amount : 

	Lane Count:   (Only if lane count is needed )

	[Below two fields will change based on information from pricing api]

	All-in-Rate: 

	Line Haul: 

	Quote Id: 

    [Flag Information  - From loadboard or Analytics Tree]

    Hazmat Flag:  

    Team Driver:

    Multi-Stop:

    [Add field that will help determine bid failure reason or manual bid or pricing augmentation] 

    Special Handling:
    
    Comments:




