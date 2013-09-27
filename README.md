*  How to find out which server holds which role:
`netdom query /domain:corp.root fsmo`

![netdom query /domain:corp.root fsmo](https://git.spigit.com/operations-team/active-directory-prep-for-2008-r2/raw/master/netdom_query.png "netdom query /domain:corp.root fsmo")

*  Verify Active Directory functionality before you apply the schema extension
`repadmin /replsum /bysrc /bydest /sort:delta`

*  Execute the forestprep on the Schema master:
`adprep32 /forestprep`

*  Before you can run adprep /domainprep, you must be sure that the updates from /forestprep have replicated to all domain controllers in the forest.

*  Execute the domainprep on each domain's Infrastructure master:
`adprep32 /domainprep`
