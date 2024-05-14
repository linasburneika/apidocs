## Reality Data API

Reality modeling is the process of capturing the physical reality of an infrastructure asset, creating a representation of it, and maintaining it through continuous surveys. Reality models add real-world digital context to infrastructure projects. The Reality Data API provides the ability to retrieve information about the reality data that is associated with an infrastructure project.

## **This API is deprecated**

The Reality Data API is deprecated and will be removed in the future, Please use the Reality Management API instead.

### RealityData

The class defines properties that describe the content of the reality data and provides an access point to the data stored in a blob container, using Microsoft Azure Storage technologies. RealityData properties represent the descriptive data related to a reality data. In addition to this, reality data content is stored as files and folders within a blob container uniquely associated to this reality data. Individual files and folders follow, from the root of the reality data, a normal file tree structure.

A more detailed documentation on RealityData properties is available [here](/apis/reality-data/rd-details/).

### Projects

RealityData are bound to Projects. Projects are used to represent engineering projects for an infrastructure asset. iModels, reality data, and engineering documents can be associated with a project. The iTwins API is used to create or query project iTwins [See more information about the iTwins API here](/apis/itwins/overview/). The Access Control API is used to manage project team members and project roles [See more information about the Access Control API here](/apis/access-control-v2/overview/).