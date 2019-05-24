WebProcess class
================

This class define a complete interface between the web browser process and the software.
It share the render area as a window identifier (as HWND under Windows).

Defined types
-------------

To work properly, the class implements many types as enumerators or structures.

 * `enum WebProcessErrorCode` : This enumerator defines all errors codes that can be pulled from `pullError` and describe the occured error. A list of the available values for this enumerator is defined as next:
 | Name | Description |
 | NO_ERROR | No error occurs from the beginning of this object life or the error was already pulled. |
 | NOT_IMPLEMENTED_ERROR | The current web engine does not have the called feature available |
 | NO_PAGE_ERROR | The current web engine does not currently have loaded web page |
 | META_TAG_NOT_FOUND | The searched meta tag is not found |
 | BAD_VALUE | A conversion went wrong because value syntax an expected type are not compatible |
