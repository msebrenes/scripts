# Why this DaemonSet?

Currently AKS does not support changing the NTP servers directly in the Node Pools.

# How can I use it?

Modify the contents in the chrony-cm.yaml starting from the _server_ line onwards. These lines can be removed and you can add all the configurations necessary as long as it is supported in the Chrony configuration. For more details, please check the official documentation: https://chrony-project.org/doc/3.4/chrony.conf.html

# Important notes
- This example requires access to a privilege pod. Using systemctl with nsenter is the only way I know of to restart services directly.
- Frecuency is set to 1 minute or 60 seconds. This can be changed in the **chrony.yaml** file in the line 29. Change `sleep 60` for your desired time.
- This example does not come with any support and it must be tested in lower environments before being deployed in critical/production clusters.

# I would like to provide feedback
Sure! Just leave a PR or Issue and I will review it as soon as I can.
