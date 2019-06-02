---
title: "WebProcess"
date: "06/01/2000"
license: "GNU GPL v3"
---

# WebEngine Class

The **WebEngine** class defines an interface between the web engine such as
Gecko or Blink and a client. It needs to be compatible with the C++ language and
must be able to operate any common graphical web engine.

For more information, see [Web Engine Usage]()

If you would interface an existing web engine, see [Integration Guidelines](#integration)
section for more informations.

## Syntax

```cpp
class WebEngine;
```

```nim
type WebEngine* = ptr object
```

### Constructors

|Constructor|Description|
|-|-|
|[WebEngine](#WebEngine)|Create a new instance of the web engine.|

### Member functions

|Member function|Description|
|-|-|
|[addInterface](#addInterface)|Add a javascript interface|
|[allowedPermissions](#allowedPermissions)|Return a list of allowed permissions for this page|
|[allowPermission](#allowPermission)|Request the activation of a permission to the current web engine|
|[devTools](#devTools)|Request the access to the developper tools interface|
|[editInterface](#editInterface)|Edit an existing javascript interface|
|[GETParameters](#GETParameters)|Return the parameters specified in the GET mode (eg. data sended through the URL)|
|[httpCode](#httpCode)|Return the last request http code|
|[httpHeader](#httpHeader)|Return the page http header|
|[httpsCertificate](#httpsCertificate)|Return all https connexion informations of the security certificate|
|[httpsState](#httpsState)|Return the httos connexion state|
|[isAllowed](#isAllowed)|Check if specified permission is allowed for the current web engine|
|[isHttps](#isHttps)|Check if the current connexion uses https instead of http|
|[isMute](#isMute)|Check if the song of the current page is mute|
|[loadPage](#loadPage)|Load a new page from the specified URL|
|[meta](#meta)|Get the value for a name from a meta tag|
|[metaList](#metaList)|Return the list of added meta tags|
|[mute](#mute)|Set if the tab is mute or not|
|[network](#network)|Get the current network manager interface from the web engine|
|[POSTParameters](#POSTParameters)|Return the parameters specified in the POST mode (eg. data sended through the page header)|
|[removeInterface](#removeInterface)|Remove an existing javascript interface|
|[rule](#rule)|Get the value of a specified rule for the web engine|
|[setNetwork](#setNetwork)|Set an other network engine to the web engine|
|[sourceCode](#sourceCode)|Get the page source code as a string variable|
|[setPermissions](#setPermissions)|Set permissions for current web page|
|[setRule](#setRule)|Set a value to a specified rule for the current web engine|
|[title](#title)|Get the current page title|
|[url](#url)|Get the current page url|

### Static functions

|Static function|Description|
|-|-|
|[defaultPermissions](#defaultPermissions)|Return the default permissions for the page|

### Member signals

> Warning, event system such as signals and slots are not available as default
> in C++. However, see [Event System Integration]() for more informations.

|Member signal|Description|
|-|-|
|[metaChanged](#metaChanged)|Sended when the meta tag list is edited|
|[newPageRequest](#newPageRequest)|Sended when the web page is changed|
|[useSound](#useSound)|Sended if the web page emit a sound|
|[pageEdited](#pageEdited)|Sended if the page structure is changed|
|[targetLink](#targetLink)|Sended if the web page attempt to load an URL to a new window/tab |
|[titleChanged](#titleChanged)|Sended if the title is changed|

## <a name="addInterface"></a> WebEngine::addInterface

**TODO**: `addInterface` member function

## <a name="allowedPermissions"></a> WebEngine::allowedPermissions

**TODO**: `allowedPermissions` member function

## <a name="allowPermission"></a> WebEngine::allowPermission

**TODO**: `allowPermission` member function

## <a name="devTools"></a> WebEngine::devTools

**TODO**: `devTools` member function

## <a name="editInterface"></a> WebEngine::editInterface

**TODO**: `editInterface` member function

## <a name="GETParameters"></a> WebEngine::GETParameters

**TODO**: `GETParameters` member function

## <a name="httpCode"></a> WebEngine::httpCode

**TODO**: `httpCode` member function

## <a name="httpHeader"></a> WebEngine::httpHeader

**TODO**: `httpHeader` member function

## <a name="httpsCertificate"></a> WebEngine::httpsCertificate

**TODO**: `httpsCertificate` member function

## <a name="httpsState"></a> WebEngine::httpsState

**TODO**: `httpsState` member function

## <a name="isAllowed"></a> WebEngine::isAllowed

**TODO**: `isAllowed` member function

## <a name="isHttps"></a> WebEngine::isHttps

**TODO**: `isHttps` member function

## <a name="isMute"></a> WebEngine::isMute

**TODO**: `isMute` member function

## <a name="loadPage"></a> WebEngine::loadPage

**TODO**: `loadPage` member function

## <a name="meta"></a> WebEngine::meta

**TODO**: `meta` member function

## <a name="metaList"></a> WebEngine::metaList

**TODO**: `metaList` member function

## <a name="mute"></a> WebEngine::mute

**TODO**: `mute` member function

## <a name="network"></a> WebEngine::network

**TODO**: `network` member function

## <a name="POSTParameters"></a> WebEngine::POSTParameters

**TODO**: `POSTParameters` member function

## <a name="removeInterface"></a> WebEngine::removeInterface

**TODO**: `removeInterface` member function

## <a name="rule"></a> WebEngine::rule

**TODO**: `rule` member function

## <a name="setNetwork"></a> WebEngine::setNetwork

**TODO**: `setNetwork` member function

## <a name="sourceCode"></a> WebEngine::sourceCode

**TODO**: `sourceCode` member function

## <a name="setPermissions"></a> WebEngine::setPermissions

**TODO**: `setPermissions` member function

## <a name="setRule"></a> WebEngine::setRule

**TODO**: `setRule` member function

## <a name="title"></a> WebEngine::title

**TODO**: `title` member function

## <a name="url"></a> WebEngine::url

**TODO**: `url` member function

## <a name="WebEngine"></a> WebEngine::WebEngine

Create a new instance of the web engine.

```cpp
WebEngine()
WebEngine(std::string url, std::vector<permissionName> permissions = WebEngine::defaultPermissions())
```

```nim
proc webEngine() : WebEngine
proc webEngine(url : string, permissions = defaultPermissions())
```

### Parameters

|Parameter|Description|
|-|-|
|url|The URL of the web page|
|permissions|The list of permissions for the page. See [permissionName]() section for more informations|
