# CustomErrorCreator
Create and manage custom errors in Labview.

Did you never had the problem that you wanted to create a custom unique error? There are several ways to manage that, and this is my proposal on how to do that using minimal overhead.
All custom errors as stored in a database. They can be created in your VI using an ExpressVI which handles the uniqueness of error code. The ExpressVI allows you to edit and select known errors and manage discepancies between code and database.

## Features
Errors are stored in a SQLite database
The next features are implemented
  
  - Unique errors are generated each time a new error is new Express VI is places
  - If errors texts are changed every VI containing the code is updated
  - History tracing of changes
  - Custom selection of storage location (could also be for example on a network location to share within a organisation or over multiple projects
  - Errors are managed over the whole LabVIEW installation
  - Errors can be made obsolete and ready for reuse if not needed anymore

# Installation
Install one of the released packages

## Additional Info
This LabVIEW library that should be placed in <LabVIEW folder>\user.lib\_express defines an Express VI that allows for managing custom error codes for LabVIEW installations.

  
# Configuration
After installation the default configuration is used
<LabVIEW folder>\user.lib\_express\CustomErrorManager\Source\CustomErrorCreator.ini

This can be edited manually or by using configuration editor in the TriekselSoft's LabVIEW Tools menu.
  
DataSetFilePath=GlobalErrorDefinition.sqlite
DefaultErrorCreationType=ErrorCreationMGI.lvclass
StartOfErrorRange=500000
EndOfErrorRange=600000

DataSetFilePath: is the filepath for the sqlite file. A absolute path can be used. Default is just the filename that results in <LabVIEW folder>\user.lib\_express\CustomErrorManager\Source\GlobalErrorDefinition.sqlite

StartOfErrorRange and EndOfErrorRange: End and Start of error range define the range in which errors are allowed to be created.

DefaultErrorCreationType: Defines how the content of the error is formatted when created. This can be overriden by defining in the project, or put the classname here. You can use the VI: <LabVIEW folder>\user.lib\_express\CustomErrorManager\Source\ErrorCreationExecution\DefineErrorCreationType.vi to set the overriding child class for error content generation
