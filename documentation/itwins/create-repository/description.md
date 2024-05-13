---

Creates a new Repository URI.

A repository is a Uri link to iTwin data managed by another service. The links for most classes are autogenerated but some can only be added manually using this POST endpoint.
      
The following Classes/SubClasses are supported. Classes in italics are auto generated. The others can be added using this POST endpoint.
- *iModels*
- *RealityData*
- *Storage*
- *Forms*
- *Issues* 
- GeographicInformationSystem
	+ WebMapService
    + WebMapTileService
    + MapServer
- ProjectWise

{!Authorization.md!}

### Authorization
The user must have the `itwins_modify` permission in order to add a repository URI to the iTwin.

An Organization Administrator can modify iTwins owned by their Organization. This includes adding a repository URI.

{!iTwinAdminOnlyAuthorization.md!}

---