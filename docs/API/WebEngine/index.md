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
