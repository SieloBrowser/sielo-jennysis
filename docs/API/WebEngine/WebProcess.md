WebProcess class
================

This class define a complete interface between the web browser process and the software.
It share the render area as a window identifier (as HWND under Windows).

Defined types
-------------

To work properly, the class implements many types as enumerators or structures.

 * <a name="error_code"></a>`enum WebProcessErrorCode` : This enumerator defines all errors codes that can be pulled from `pullError` and describe the occured error. A list of the available values for this enumerator is defined as follows:
 
| Name                  | Description                                                                             |
| --------------------- | --------------------------------------------------------------------------------------- |
| NO_ERROR              | No error occurs from the beginning of this object life or the error was already pulled. |
| NOT_IMPLEMENTED_ERROR | The current web engine does not have the called feature available                       |
| NO_PAGE_ERROR         | The current web engine does not currently have loaded web page                          |
| META_TAG_NOT_FOUND    | The searched meta tag is not found                                                      |
| BAD_VALUE             | A conversion went wrong because value syntax an expected type are not compatible        |

 * `enum WebProcessLoadState` : This enumerator defines all states that can be used by the web engine. A list of the available values for this enumerator is defined as follows:

| Name     | Description                                                                                         |
| -------- | --------------------------------------------------------------------------------------------------- |
| WORKING  | The web engine is currently working. e.g. it can render page and refresh its rendering              |
| UNLOADED | The web engine is unloaded. e.g. the web engine process doesn't run and the page doesn't use memory |
| BUSY     | The web engine does not currently respond.                                                          |

 * `typedef WinID` : This type is an overload of an integer and specify the identifier of the browser view window. This identifier needs to be accessible to the GUI module because it is the only one object which link the rendering area to the window. This type needs to be an overload of:
     * `HWND` for Win32 API compatible Operating System (Windows 10, Windows 8, Windows 7...)
     * `int` for Cocoa API compatible Operating System (MacOS 10.0 and above)
     * `long` for X.org/Wayland compatible Operating System (Linux for desktop)

Methods
-------

An object is a collection of methods and parameters used to make complex tasks. In this case, this object implements these methods:

 * **Constructor**: This function create a new instance of this object.
 * **Destructor**: This function destroy the current instance of the object and is called when the developper calls `delete <object name>` in C++.
 * **`DevTools developerTools()`**: This function gives the developper tools client framework.
 * **`WebProcessLoadState loadState() const`**: This function return the current web engine state.
 * **`string metaValue(string name) const`**: This function give the value of a meta tag with as name `name`.
 * **`ifstream pageCode() const`**: This function give an input flux (e.g. the flux can't be edited by the client) of the source code of loaded page.
 * **`string pageTitle() const`**: This function give the current page title.
 * **`WebProcessErrorCode pullError()`**: This function get the last appened error. If the last error was pulled or nothing append from the initializing of this object, this function returns `NO_ERROR`. See [error code section](#error_code) for more informations.
 * **`WinID winID()`**: This function provides the window identifier to be given to the GUI module.

Attributes
----------

Attributes sets up getter and setters for the object. These attributes are defined as follows:

 * `WebPermissions permissions`: This attribute is a list of a permission allowed to a web page

 * `WebFeatures features`: This attribute is a list of features supported by the web engine.

**Note:** each web engine has its own features list. As a consequence, please read the documentation of this last to know what are available permissions.