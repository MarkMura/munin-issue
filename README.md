# munin-issue
debugging setup to investigate https://github.com/munin-monitoring/munin/issues/1109

In this configuration, munin master fails to connect to munin node with error message `Failed to connect to node testnode:4949/tcp : No such file or directory` (doesn't say which file or directory...)

But by installing munin-node package into the master container, it magically starts to work without any problem.
