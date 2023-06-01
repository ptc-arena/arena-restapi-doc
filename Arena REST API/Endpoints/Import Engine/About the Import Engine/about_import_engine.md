# About the Import Engine
Along with the Event Engine and Export Engine \(initially introduced as API Export\), the Import Engine is the third installment of the Integration Engine, whose goal is to allow integrations to seamlessly obtain and load data to and from Arena while notifying external systems about events within an Arena workspace.

**The Import Engine is ONLY available in workspaces with Access Policies enabled** .

As the counterpart to the Export Engine, the Import Engine supports the loading of  data through Arena’s API.

Imports are defined in an import definition POST endpoint. The request body of an import definition POST endpoint defines the import resource, supported options, the mode, and the mapping behavior for the import.

With this import definition GUID \(generated from the import definition POST endpoint\), any user with the appropriate access can run an API import with the specific resources, options, and mapping behavior specified within this specific import definition.

With the import definition GUID in hand, the next step would be to create a source file. The Import Engine currently supports the XLSX or CSV \(adhering to RFC-4180\) file formats. Note that the column names of the source file adhere to the names listed within the mapping section of the import definition.

Once the source file is ready, the user can then execute the import through an import run POST endpoint. The user then inputs the import definition GUID within the URL of the import run endpoint and uploads the source file as a form-data content-type  and then executes the endpoint.

In addition to the previously mentioned POST endpoints, additional Import Engine endpoints allow users to search for definitions, edit definitions, search for previous import runs, retrieve a source file from a previous import run, retrieve the results of an import run, and retrieve the errors of an import run.

Users can even validate an import before importing it into a workspace by creating an import definition with a value of false for the attribute commit. After checking for errors, users can then commit and complete the import using a PUT endpoint.

