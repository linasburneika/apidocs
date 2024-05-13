---

Acquires requested locks on specified objects.
Lock - the right to modify a specific type of data within the iModel. For more information on Locks [see working with Locks via iTwin.js client libraries](https://www.itwinjs.org/learning/backend/concurrencycontrol/#pessimistic-concurrency-control).

**Note:** Lock types have been removed for this API and should be ignored.

**Object ids Limit:** Currently there can be at most 1000 object ids in a single request.

{!Authorization.md!}

### Authorization

To release any Locks (set `LockLevel` to `none`) user must have `imodels_manage` permission assigned at the iModel level. If permissions at the iModel level are not configured, then user must have `imodels_manage` permission assigned at the iTwin level. To acquire or realese Locks that the user owns `imodels_write` permission is enough.

Alternatively the user should be an Organization Administrator for the Organization that owns a given iTwin the iModel belongs to.

An Organization Administrator must have at least one of the following roles assigned in User Management: Account Administrator, Co-Administrator, or CONNECT Services Administrator. For more information about User Management please visit our Bentley Communities [Licensing, Cloud, and Web Services](https://communities.bentley.com/communities/other_communities/licensing_cloud_and_web_services/w/wiki/50711/user-management-2-0) wiki page.

{!RateLimits.md!}

---
