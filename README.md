# data-ops-mle-challenge

Hi there!

Here's a quick challenge for you to demonstrate your skills as a DataOps or Machine Learning Engineer. This is intended to be quick, light, easy, and fun - don't stress or spend too much time here! When done, feel free to share your solution via Github or other version control system.

## Problem

We have a sample model for predicing the price of Bitcoin in the next second based on the prices from the last 60 seconds whipped up by one of our data scientists - this is a quick and dirty model, wrapped in a quick and dirty API, packaged into a quick and dirty container, and we've decided to YOLO and test in prod.

Tasks:
* This is really quick and dirty - how would you do this better?
* Come up with tests for container or requests failure
* Come up with tests for data quality in this context
* Introduce slack alerts for failure of either of the above. Here's some sample code:

'''

    execution_frequency_minutes = 5
    slack_channel = getenv("OPS_NOTIFICATIONS_SLACK_CHANNEL", "debug-slackbot")
    # Ops only wants a single notification for the user for this check, even if they have subsequent rolling 24 hour deposits exceeding the `total_deposit_threshold`
    notification_deduping_row_keys = ['user_id', 'pam_user_id']

'''

Questions for you to consider:

* Does this data set even make sense? What's wrong with it?
* What makes this model unsuitable for inferencing in prod?
* How would you validate the model inputs in this container?
* What happens with this container if the model and API take more than a second to return a response?
* What would happen if the price of bitcoin suddenly shot up by $10k at 3am? Would this model still be good? How would we catch this?