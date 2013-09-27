*  How to find out which server holds which role:
`netdom query /domain:corp.root fsmo`

![netdom query /domain:corp.root fsmo](https://raw.github.com/jasonwbarnett/Active-Directory-Prep-for-2008-R2/master/netdom_query.jpg "netdom query /domain:corp.root fsmo")

*  Verify Active Directory functionality before you apply the schema extension
`repadmin /replsum /bysrc /bydest /sort:delta`

*  Here is a copy of the support folder from the en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso which contains the adprep and adprep32 binaries
[support_from_en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso.zip](http://cloud.ja.sonbarnett.com/3L3J063g3j1S/download/support_from_en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso.zip)

*  Execute the forestprep on the __Schema master__:
`adprep /forestprep` or `adprep32 /forestprep`

*  Before you can run adprep /domainprep, you must be sure that the updates from /forestprep have replicated to ALL domain controllers in the forest.

*  Execute the following command once for __each__ domain in the forest on the domain's  __Infrastructure master__:
`adprep /domainprep` or `adprep32 /domainprep`
