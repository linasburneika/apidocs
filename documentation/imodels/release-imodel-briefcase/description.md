---

Deletes the specified [Briefcase](https://www.itwinjs.org/learning/glossary/#briefcase).

Briefcases are the local copies of iModel that users can acquire to work with the iModel. Users can make changes to their copy of iModel and then push them as a single Changeset file into iModelHub. For more information on Briefcases see [working with Briefcases](https://www.itwinjs.org/learning/imodelhub/briefcases/).

{!Authorization.md!}

### Authorization

To release any Briefcase user must have `imodels_manage` permission assigned at the iModel level. If permissions at the iModel level are not configured, then user must have `imodels_manage` permission assigned at the iTwin level. To release a Briefcase that the user owns `imodels_webview` permission is enough.

Alternatively the user should be an Organization Administrator for the Organization that owns a given iTwin the iModel belongs to.

An Organization Administrator must have at least one of the following roles assigned in User Management: Account Administrator, Co-Administrator, or CONNECT Services Administrator. For more information about User Management please visit our Bentley Communities [Licensing, Cloud, and Web Services](https://communities.bentley.com/communities/other_communities/licensing_cloud_and_web_services/w/wiki/50711/user-management-2-0) wiki page.

{!RateLimits.md!}

---