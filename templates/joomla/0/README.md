# Joomla!

### Info:

Joomla! is an award-winning content management system (CMS), which enables you to build Web sites and powerful online applications. Many aspects, including its ease-of-use and extensibility, have made Joomla! the most popular Web site software available. Best of all, Joomla is an open source solution that is freely available to everyone.

### Scale:

To scale this solution, add a convoy-gluster volume to share the data between the instances, or use a local path with a custom solution to share the data.

When specifying the "Data volume" path an colon ( : ) needs to be added to the end of the path, as this adds the option not to bind to a local volume.
---
/var/lib/docker/joomla:
---