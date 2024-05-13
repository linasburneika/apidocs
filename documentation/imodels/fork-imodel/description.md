---

Creates an iModel Fork. An iModel Fork is a new iModel which is a full or partial clone of the source iModel, but the difference between an iModel Fork and an iModel clone is that Fork iModels can be edited and then merged back to the source iModel.

### Relationship between source and Fork iModels

An iModel Fork is a valid standalone iModel. An iModel Fork is not deleted if the source iModel is deleted.

When the iModel forking process is completed, no new changes are synchronized to the iModel Fork from the source iModel.

[iModel Create Operation Details](https://dev-developer.bentley.com/apis/imodels-v2/operations/get-create-imodel-operation-details/) operation can be used to determine if the current iModel is a Fork.

### iModel Fork content and metadata

The iModel Fork name and description can be specified when forking an iModel, by default name and description are taken from the source iModel. iModel extent is always taken from the source iModel.

[iModel Baseline](https://developer.bentley.com/apis/imodels-v2/operations/get-imodel-baseline-file-details/) is always copied from the source iModel to the iModel Fork. User can specify until which point [Changesets](https://developer.bentley.com/apis/imodels-v2/operations/get-imodel-changesets/) should be copied to the iModel Fork, by default all source iModel Changesets are copied. The rest of source iModel entities are not copied.

### Operation state

Forking an iModel is an asynchronous operation. To check the status of the operation please follow the link present in `Create-iModel-Operation` response header. The link points to [Get Create iModel Operation details](https://developer.bentley.com/apis/imodels-v2/operations/get-create-imodel-operation-details/) endpoint of the iModel Fork. When the iModel Fork's Create Operation `state` property is set to `successful` it means the forking process is complete and iModel is ready to be used.

#### `sourceIsMissingFederationGuids` state

If `state` returned by [Get Create iModel Operation details](https://developer.bentley.com/apis/imodels-v2/operations/get-create-imodel-operation-details/) is equal to `sourceIsMissingFederationGuids`, it means that iModel Fork creation failed because some elements in the source iModel do not have [FederationGuid](https://www.itwinjs.org/bis/guide/fundamentals/federationguids/) property set. In order to proceed users must populate missing FederationGuid values and retry the iModel Fork creation request.

{!Authorization.md!}

### Authorization

User must have the following permissions:
- `imodels_manage` permission at the source iModel iTwin level.
- `imodels_manage` permission at the iTwin, in which the iModel Fork will be created, level.

If source iModel has iModel level permissions configured, then user must have at least `imodels_webview` permission assigned.

Alternatively the user should be an Organization Administrator both for the Organization that owns source iModel iTwin and the Organization that owns the Fork iModel iTwin.

{!OrganizationAdministrator.md!}

**Important**: Fork iModel operation is in closed preview mode currently and only selected applications can utilize it.

### Rate limits

This operation has a lower rate limit than the rest of iModels API operations. If an application exceeds the rate limit it will receive an HTTP error code 429 "Too Many Requests". The error response includes a Retry-After header that indicates how long clients should wait before retrying.

| Tier                       | Rate limit          |
| -------------------------- | ------------------- |
| Trial                      | 5 calls per minute  |
| Basic, Premium, Enterprise | 20 calls per minute |
<br/>
---
