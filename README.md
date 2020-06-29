# email_distribution
Step 1 - import / create your distribution list and pin it to Connect. (pin_dist_list.rmd)  
Step 2 - create your email and use `blastula::smtp_send()` to send your email (send_email.rmd).   
Step 3 - publish send_email.rmd to Connect and schedule the output. 

Things to be aware of:
* When you publish send_email.rmd to Connect the first time, it will send the email as it renders.  So if you don't want everyone to get the email before the scheduled time, ensure your pinned distribution list is empty first.   
* In `smtp_send`, everyone in the `to` argument will be in the to line of the email sent. If you want to suppress the recipients, use bcc.  If you want individual recipients in the to line, try `purrr::map` to iteratively do sent_smtp to each recipient.  There are probably other more elegant solutions.  
* Speaking of more elegant ways, I'm sure this whole thing could be more elegant.  But this is what happens late at night when I've got 2 hours to spare :). 
