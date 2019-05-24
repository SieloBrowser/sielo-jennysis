WebEngine integration API
=========================

Abstract
--------

Sielo Browser is designed to run some web engine.
As a consequence, an architecture built around one web engine is unbelievable.
As a consequence, it is required to create an API designed to link a Web engine such as Webkit and Sielo.

For versatility purposes, this API needs to work without any graphical user interface API other than native libraries
such as Win32 API for Windows or Xorg/Wayland API for Linux.
As a consequence, only the Widget identifier is shared by this API without any other graphical content.

Error handing
-------------

Each object provides a standard error handling function called `pullError`.
This function return the error code when called or NO_ERROR if nothing appened since the last function call.
When this function is called, the error code is deleted.

Objects
-------

This API is split between two main objects packaged under one namespace
named `WebEngine`. These objects are defined as follows:
 * **The [WebProcess](WebProcess) object:** This object manages all process used by this web engine. It is able to create and kill any process and view processor and memory use for each of these.
 * **The [DevTools](DevTools) object:** This object defines the interface between the developer tools server in the web engine and the developer tools client provided by Sielo.
 
In order to allow a smart communication with this module, some objects are also defined as follows:
 * **The [WebPermissions](WebPermissions) object:** This object is a container of permission of a page between web engine process and web page.
 * **The [WebFeatures](WebFeatures) object:** This object is a list of features available and enabled for the current web engine such as experimental feature.
