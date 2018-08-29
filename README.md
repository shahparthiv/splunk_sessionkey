# splunk_sessionkey

How to get the sessionkey in scripted input python file?

First of all we need to write the following properties in our stanza of inputs.conf.

```
[script://$SPLUNK_HOME/etc/apps/parthiv_app/bin/test.py]
disabled = false
interval = -1
passAuth = splunk-system-user
sourcetype = _json
```
So according to this stanza our python file is test.py.
and interval = -1 means this script will run at every restart.

Plus, it is mendatory to add passAuth property to get sessionkey in the test.py.

Now update the test.py as below:

```
import os
import sys

sessionKey = sys.stdin.read()

```

Thanks,
