# what is root var ?
/var stores variable data such as logs, caches, queues and application data.

/var mein frequently change hone wala data store hota hai, especially logs.

# Important location:

/var/log/

# Examples:

/var/log/auth.log

/var/log/syslog

Distribution ke according log file names/location different ho sakte hain.

# SOC Analyst ke liye

Ye directory bahut important hai.

Agar kisi system par suspicious login hua hai, analyst logs investigate kar sakta hai:

</bash>

sudo cat /var/log/auth.log

Ya:

</bash>

sudo tail -f /var/log/auth.log
