# About
Push or Pull todo items to and from Google Tasks.

Examples:
<pre><code>$ todo.sh google pull       #pulls tasks from Google
$ todo.sh google push       #push todo items to Google
$ todo.sh google push all   #push todo and done items to Google
</code></pre>

# Installation
- Install Python 2. (This addon currently does NOT work with Python 3.)
- Download the addon script and put into your todo.actions.d folder

### Enable Google API Access
- Create a project in the Google APIs Console (http://code.google.com/apis/console).
- Under "APIs" enable the Tasks API
- Under "Credentials" create a new Client Id for an installed application
- Enter the Google-provided Client ID and Client Secret in the variables at the start of the addon script.

### Install Dependencies
```bash
$ cd ~/.todo.actions.d
$ pip install -r requirements.txt
```

Alternatively,
```bash
$ pip install google-api-python-client
$ pip install python-gflags
```
or manually install from https://developers.google.com/api-client-library/python/

# Notes:
Note that for simplicity, the 'archive' command is executed prior to the sync.

- 'pull' will fetch google tasks and add them to your todo and done lists. Tasks will be pulled from all Google Task lists
- 'push' command will push your todo list from todo.txt to Google Tasks
- 'push all' command will push items from both todo.txt and done.txt

Currently all new tasks will be added to the default Google Task list. (This may change in the future)

As this is a pull/push, there are obviously limitations to the syncing. For instance an already pushed  todo that is editted considerably will get pushed as a separate task as there is no way to match old and new. I've tried to allow for some of the more common and minor changes, such as marking a todo with a priority. Also, completing a todo or task can be synced up or down accordingly.
