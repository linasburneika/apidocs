### Inactive iTwins
iTwins with *status=Inactive* are not returned by default. This improves query performance and reduces clutter in user interfaces by filtering out unused iTwins. 
You should still provide a way for users to see their Inactive iTwins if they request them. In the API, you can do this by setting the status parameter or by using the includeInactive parameter.

If *status=Inactive*, the API will return only Inactive iTwins.  
If *includeInactive=true*, the API will return all iTwins (Active, Trial and Inactive).

The includeInactive parameter is optional and defaults to false. A 422 error will be returned if you try to use a status parameter at the same time as the includeInactive parameter.