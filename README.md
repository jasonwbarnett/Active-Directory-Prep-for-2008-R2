*  How to find out which server holds which role:
`netdom query /domain:corp.root fsmo`

![netdom query /domain:corp.root fsmo](https://git.spigit.com/operations-team/active-directory-prep-for-2008-r2/raw/master/netdom_query.png "netdom query /domain:corp.root fsmo")

*  Verify Active Directory functionality before you apply the schema extension
`repadmin /replsum /bysrc /bydest /sort:delta`

*  Here is a copy of the support folder from the en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso which contains the adprep and adprep32 binaries
[support_from_en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso.rar](http://cloud.ja.sonbarnett.com/3X2i2I3h0d1o/download/support_from_en_windows_server_2008_r2_with_sp1_x64_dvd_617601.iso.rar)

*  Execute the forestprep on the Schema master:
`adprep32 /forestprep`

*  Before you can run adprep /domainprep, you must be sure that the updates from /forestprep have replicated to all domain controllers in the forest.

*  Execute the domainprep on each domain's Infrastructure master:
`adprep32 /domainprep`
