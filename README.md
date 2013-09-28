*  How to find out which server holds which role:
`netdom query /domain:corp.root fsmo`

![netdom query /domain:corp.root fsmo](https://raw.github.com/jasonwbarnett/Active-Directory-Prep-for-2008-R2/master/netdom_query.jpg "netdom query /domain:corp.root fsmo")

*  Verify Active Directory functionality before you apply the schema extension
`repadmin /replsum /bysrc /bydest /sort:delta`

*  Here is a copy of the support folder from the en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso which contains the adprep and adprep32 binaries
[support_from_en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso.zip](http://cloud.ja.sonbarnett.com/3L3J063g3j1S/download/support_from_en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso.zip)

*  Required roles of user running /forestprep: Schema Admins group, the Enterprise Admins group, and the Domain Admins group of the domain that hosts the schema master. [Windows Reference](http://technet.microsoft.com/en-us/library/dd464018.aspx#BKMK_R2Adprep)

*  You may need to move the Schema owner role to a new domain controller in order to make it possible for a single user to be in all 3 required groups. [This doc](http://support.microsoft.com/kb/324801/en-us) describes how to transfer the Schema owner role to a new domain controller.

*  Execute the forestprep on the __Schema master__:
`adprep /forestprep` or `adprep32 /forestprep`

*  Before you can run adprep /domainprep, you must be sure that the updates from /forestprep have replicated to ALL domain controllers in the forest. Below are some helpful commands for checking on the replication.
`repadmin /showrepl`
`repadmin /replsummary`
`dcdiag`

*  Execute the following command once for __each__ domain in the forest on the domain's  __Infrastructure master__:
`adprep /domainprep` or `adprep32 /domainprep`
