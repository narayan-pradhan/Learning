
### Use the lsid, badmin, bparams, and lsclusters commands to find information about the LSF cluster.
## Procedure
Cluster information includes the cluster management host, cluster name, cluster resource definitions, cluster administrator, and other details.
Table 1. LSF commands to view cluster information
|View| Command |
|----| ----| 
|Version of LSF |	lsid|
|Cluster name|	lsid|
|Current management host|	lsid|
|Cluster administrators|	lsclusters|
|Configuration parameters|	bparams|
|LSF system runtime information|	badmin showstatus|

# Submit a job to specific hosts
Specify which hosts a job can run on.
## Procedure
To indicate that a job must run on one of the specified hosts, use the bsub -m "hostA hostB ..." option.
For example:
>bsub -m "hostA hostD hostB" myjob

Running interactive job with lsf
>bsub -I -m "hostname" "command"

### Use the lsadmin and badmin commands to reconfigure LSF after you change any configuration file.
## Procedure
1. Log in as root to each LSF server host.
 If you installed a single-user cluster as a non-root user, log in as primary LSF administrator.
2. Use the following commands to reconfigure the LSF cluster:
- Reload modified LSF configuration files and restart lim: 
 \# lsadmin reconfig
- Reload modified LSF batch configuration files:
\# badmin reconfig
- Reload modified LSF batch configuration files and restart mbatchd:
\# badmin mbdrestart

This command also reads the LSF_LOGDIR/lsb.events file, so it can take some time to complete if a lot of jobs are running.

## Useful links
- [Reconfiguring your cluster with lsadmin and badmin]
- [Solving common LSF problems]
- [LSF error messages]
- [Troubleshooting and Error Messages]
- [Working with Hosts]
- [Hosts]



  [Reconfiguring your cluster with lsadmin and badmin]: <https://www.ibm.com/support/knowledgecenter/SSWRJV_10.1.0/lsf_admin_foundations/reconfig_cluster.html>
  [Solving common LSF problems]: <https://www.ibm.com/support/knowledgecenter/SSWRJV_10.1.0/lsf_admin/troubleshooting_common_problems_lsf.html> 
  [LSF error messages]: <https://www.ibm.com/support/knowledgecenter/SSWRJV_10.1.0/lsf_admin/troubleshooting_error_messages_lsf.html>
  [Troubleshooting and Error Messages]: <http://sunray2.mit.edu/kits/platform-lsf/7.0.6/1/guides/kit_lsf_guide_source/admin/troubleshooting.html>
  [Working with Hosts]: <http://sunray2.mit.edu/kits/platform-lsf/7.0.6/1/guides/kit_lsf_guide_source/admin/manage_hosts.html#wp256148>
  [Hosts]: <https://www.ibm.com/support/knowledgecenter/SSWRJV_10.1.0/lsf_users_guide/hosts_about.html>
