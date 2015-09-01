reddit-deletion-checker-rbtv
=======================

This is an open-source /r/undelete clone written in Python **3**.

Requirements
------------

 - **You must be running Python 3.**
 - **You must put your username in the "bot_operator" variable at the top of the script.**
 - **You must add your OAuth Codes in a new file called "tokens.py"**

In Linux (and Mac OS X?), you can run the code with `python3 deletion-checker-rbtv.py`.

In Windows, open the script up in the Python **3** version of IDLE, and press F5. Or, run it from the command line as above.

You will also need some pip packages:  

    pip install praw
    pip install prawoauth2

The tokens.py should look like this:

    app_key = "YOUR APP KEY"
    app_secret = "YOUR APP SECRET"
    access_token = "YOUR OAUTH ACCESS TOKEN"
    refresh_token = "YOUR OAUTH REFRESH TOKEN"

Notes
-----

 - This script displays all deletions and post it into another subreddit like /r/undelete.
 - This has only been tested very shortly and only in my linux installation. It's probably nowhere near perfect. **(see the "known issues")**
 - I used a sqlite database, but that's probably not even necessary. Oh well. Someone else can make it more efficient.

Known issues
------------

I've seen some false positives (where this script reported something has been deleted when it really hasn't) - I think it's a result of the way I have to access the pages of /r/all. The false positives I've seen were all in the high 90s in rank (near the bottom of the page), and I guess something was weird when the script went to re-check the posts.

In other words, if you see something being reported as deleted and it's not on /r/undelete or /r/longtail ***and*** its rank is near a multiple of 100, don't go freaking out about /r/undelete censorship. It's probably just my script being a little weird.

This issue is somewhat amplified in the longtail mode of this script (simply because it's checking 10x the pages).

Credits
-----

The most of this code was developed by [ozys](https://github.com/ozys/reddit-deletion-checker)  
Thank you for that!

License
-------

The source code is released under CC0 v1.0, which is effectively a dedication to the public domain to the extent allowed by law.

For more information, see [https://creativecommons.org/publicdomain/zero/1.0/](https://creativecommons.org/publicdomain/zero/1.0/) and [https://creativecommons.org/publicdomain/zero/1.0/legalcode](https://creativecommons.org/publicdomain/zero/1.0/legalcode).

See also the LICENSE file in this repository.
