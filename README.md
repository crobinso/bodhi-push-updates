Helper script for pushing Fedora [bodhi](https://admin.fedoraproject.org/updates) updates from testing to stable. When you get emails that you're updates have hit the testing timeout and can be pushed to stable, run this script and interactively decide which updates you want to push.

Basically works like this:

* Query all your pending updates
* Filter out the ones that haven't reached the testing timeout, by looking for the 'can be pushed to stable' comment from bodhi.
* For each appropriate update:
    * Show the update karma
    * Filter out bodhi process comments ('pushed to testing' etc.)
    * Filter out PASSED taskotron messages
    * Show the remaining comments
    * Prompt the user if they'd like to push this update to stable
* Push all the requested updates to stable

So if you push a lot of updates this can save a bit of time clicking around in the web UI or invoking bodhi manually from the command line.
