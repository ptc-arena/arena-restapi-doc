# About Criteria and Options in API Export
In API Export, export options determine which details of an Item is returned. Export options can only be defined in the export definition. Similar to Item export settings within the user interface, options determine which Item views, BOM levels, and revisions of Items are exported. 

Export criteria determine which Items are exported. If export options resemble the export settings, criteria would most resemble Arena Advanced Search. Similar to Advanced Search, users can build complex criteria connected to each other in groups through logical operators.

Export criteria can be specified in the export definition call or in the export run call, but it cannot be  specified in both. If  an export definition contains specified criteria, then it cannot be edited because export definitions cannot be edited.  If an export definition  does not specify criteria, then criteria can be specified in the export run call. You can specify multiple  source relationships for an Item in the Relationships subview of the Sourcing view. See export endpoints for examples of export definition and export run calls. 

