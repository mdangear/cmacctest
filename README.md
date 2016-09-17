# cmacctest
Sample files for Cmacc

Files are working with the electron editor that can be downloaded from common-accord repo.

Syntax is slightly changed from generic CommonAccord, to allow better/easier editing of content, including debugging for docs

To set parameters:

$ key = value

To call a file

$ key = [link to file] => {
 "key" : value
}

This syntax does not allow inheritance injection, so a key cannot be set to another key.
This is a restriction from the generic CommonAccord model, as a compromise for performance and editing/debugging capabilities.
