# CustomErrorCreator
Create and manage custom errors in Labview

This LabVIEW library that should be placed in <LabVIEW folder>\user.lib\_express defines an Express VI that allows for managing custom error codes for LabVIEW installations.
Errors are stored in a SQLite database
The next features are implemented
  
  - Unique errors are generated each time a new error is new Express VI is places
  - Errors are grouped by libary (lvlib or lvclass)
  - If errors texts are changed every VI in the library containing the code is updated
  - A SQLite database is used as a source with history tracing of changes.
  
