1. How to find out which server holds which role:
`netdom query /domain:corp.root fsmo`

![netdom query /domain:corp.root fsmo](./netdom_query.png)

2. Verify Active Directory functionality before you apply the schema extension
`repadmin /replsum /bysrc /bydest /sort:delta`

3. Execute the forestprep on the Schema master:
`adprep32 /forestprep`

4. Before you can run adprep /domainprep, you must be sure that the updates from /forestprep have replicated to all domain controllers in the forest.

5. Execute the domainprep on each domain's Infrastructure master:
`adprep32 /domainprep`
