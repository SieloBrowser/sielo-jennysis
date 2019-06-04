---
title: "WebProcess Class"
date: "06/01/2000"
license: "CC-BY-NA"
---

# WebProcess Class

The **WebProcess** class defines an interface between the web engine such as
Gecko or Blink and a client. It needs to be compatible with the C++ language and
must be able to operate any common graphical web engine.

For more information, see [Web Engine Usage]()

If you would interface an existing web engine, see [Integration Guidelines](#integration)
section for more informations.

## Syntax

```cpp
class WebProcess;
```

```nim
type
  WebProcess* {.bycopy.} = object
```

### Constructors

|Constructor|Description|
|-|-|
|[WebProcess](#WebProcess)|Create a new instance of the web engine.|

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
|[httpsState](#httpsState)|Return the https connexion state|
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
|[winId](#winId)|Get the window indentifier of the rendering area|

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

## Requirements

### In C++

**Include**: `<WebEngine.hpp>`

**Namespace**: `Sielo::WebEngine`

### In NIM

**Import**: `WebEngine`

## <a name="addInterface"></a> WebProcess::addInterface

Add a javascript interface

```cpp
bool WebProcess::addInterface(std::string name, JSInterface interface);
```

```nim
proc addInterface*(this : var WebProcess, name : string, interface : JSInterface) : bool
```

### Parameters

|Parameter|Description|
|-|-|
|name|The name of the interface (e.g the root object where interface is called)|
|[JSInterface](JSInterface.md)|A javascript interface handler type.|

### Returns

`true` if the interface is successfully created of `false` else.
`false` is returned if the interface already exists or it name is reserved.

## <a name="allowedPermissions"></a> WebProcess::allowedPermissions

Return a list of allowed permissions for this page

```cpp
std::vector<permissionName> WebProcess::allowedPermissions(void) const;
```

```nim
proc allowedPermissions*(this : var WebProcess) : vector[permissionName]
```

**TODO**: `allowedPermissions` member function

## <a name="allowPermission"></a> WebProcess::allowPermission

Request the activation of a permission to the current web engine

```cpp
void WebProcess::allowPermission(permissionName permission, bool enabled);
```

```nim
proc allowPermission*(this : var WebProcess, permission : permissionName, enabled : bool)
```

**TODO**: `allowPermission` member function

## <a name="devTools"></a> WebProcess::devTools

Request the access to the developper tools interface

```cpp
std::weak_ptr<WebDevTools> WebProcess::devTools(void) const;
```

```nim
proc devTools*(this : var WebProcess) : weak_ptr[WebDevTools]
```

**TODO**: `devTools` member function

## <a name="editInterface"></a> WebProcess::editInterface

Edit an existing javascript interface

```cpp
bool WebProcess::editInterface(std::string name, JSInterface interface);
```

```nim
proc editInterface*(this : var WebProcess, name : string, interface : JSInterface) : bool
```

**TODO**: `editInterface` member function

## <a name="GETParameters"></a> WebProcess::GETParameters

Return the parameters specified in the GET mode (eg. data sended through the URL)

```cpp
std::map<std::string, std::string> WebProcess::GETParameters(void) const;
```

```nim
proc GETParameters*(this : var WebProcess) : map[string, string]
```

**TODO**: `GETParameters` member function

## <a name="httpCode"></a> WebProcess::httpCode

Return the last request http code

```cpp
int WebProcess::httpCode(void) const
```

```nim
proc httpCode*(this : var WebProcess) : cint
```

**TODO**: `httpCode` member function

## <a name="httpHeader"></a> WebProcess::httpHeader

Return the page http header

```cpp
std::string WebProcess::httpHeader(void) const;
```

```nim
proc httpHeader*(this : var WebProcess) : string
```

**TODO**: `httpHeader` member function

## <a name="httpsCertificate"></a> WebProcess::httpsCertificate

Return all https connexion informations of the security certificate

```cpp
httpsCertificateData WebProcess::httpsCertificate(void) const;
```

```nim
proc httpsCertificate*(this : var WebProcess) : httpsCertificateData
```

**TODO**: `httpsCertificate` member function

## <a name="httpsState"></a> WebProcess::httpsState

Return the https connexion state

```cpp
httpsStateCode WebProcess::httpsState(void) const;
```

```nim
proc httpsState*(this : var WebProcess) : httpsStateCode
```

**TODO**: `httpsState` member function

## <a name="isAllowed"></a> WebProcess::isAllowed

Check if specified permission is allowed for the current web engine

```cpp
bool WebProcess::isAllowed(permissionName permission) const;
```

```nim
proc isAllowed*(this : var WebProcess, permission : permissionName) : bool
```

**TODO**: `isAllowed` member function

## <a name="isHttps"></a> WebProcess::isHttps

Check if the current connexion uses https instead of http

```cpp
bool WebProcess::isHttps(void) const;
```

```nim
proc isHttps*(this : var WebProcess) : bool
```

**TODO**: `isHttps` member function

## <a name="isMute"></a> WebProcess::isMute

Check if the song of the current page is mute

```cpp
bool WebProcess::isMute(void) const;
```

```nim
proc isMute*(this : var WebProcess) : bool
```

**TODO**: `isMute` member function

## <a name="loadPage"></a> WebProcess::loadPage

Load a new page from the specified URL

```cpp
bool WebProcess::loadPage(std::string url);
```

```nim
proc loadPage*(this : var WebProcess, url : string) : bool
```

**TODO**: `loadPage` member function

## <a name="meta"></a> WebProcess::meta

Get the value for a name from a meta tag

```cpp
std::string WebProcess::meta(std::string name) const;
```

```nim
proc meta*(this : var WebProcess, name : string) : string
```

**TODO**: `meta` member function

## <a name="metaList"></a> WebProcess::metaList

Return the list of added meta tags

```cpp
std::map<std::string, std::string> WebProcess::metaList(void) const;
```

```nim
proc metaList*(this : var WebProcess) : map[string, string]
```

**TODO**: `metaList` member function

## <a name="mute"></a> WebProcess::mute

Set if the tab is mute or not

```cpp
void WebProcess::mute(bool mute);
```

```nim
proc mute*(this : var WebProcess, mute : bool)
```

**TODO**: `mute` member function

## <a name="network"></a> WebProcess::network

Get the current network manager interface from the web engine

```cpp
std::weak_ptr<NetworkEngine> WebProcess::network(void) const;
```

```nim
proc network*(this : var WebProcess) : weak_ptr[NetworkEngine]
```

**TODO**: `network` member function

## <a name="POSTParameters"></a> WebProcess::POSTParameters

Return the parameters specified in the POST mode (eg. data sended through the page header)

```cpp
std::map<std::string, std::string> WebProcess::POSTParameters(void) const;
```

```nim
proc POSTParameters*(this : var WebProcess) : map[string, string]
```

**TODO**: `POSTParameters` member function

## <a name="removeInterface"></a> WebProcess::removeInterface

Remove an existing javascript interface

```cpp
bool WebProcess::removeInterface(std::string name);
```

```nim
proc removeInterface*(this : var WebProcess, name : string) : bool
```

**TODO**: `removeInterface` member function

## <a name="rule"></a> WebProcess::rule

Get the value of a specified rule for the web engine

```cpp
int WebProcess::rule(ruleName rule) const;
```

```nim
proc rule*(this : var WebProcess, rule : ruleName) : cint
```

**TODO**: `rule` member function

## <a name="setNetwork"></a> WebProcess::setNetwork

Set an other network engine to the web engine

```cpp
void WebProcess::setNetwork(std::shared_ptr<NetworkEngine> net);
```

```nim
proc setNetwork*(this : var WebProcess, net : shared_ptr[NetworkEngine])
```

**TODO**: `setNetwork` member function

## <a name="sourceCode"></a> WebProcess::sourceCode

Get the page source code as a string variable

```cpp
std::string WebProcess::sourceCode(void) const;
```

```nim
proc sourceCode*(this : var WebProcess) : string
```

**TODO**: `sourceCode` member function

## <a name="setPermissions"></a> WebProcess::setPermissions

Set permissions for current web page

```cpp
void WebProcess::setPermissions(std::vector<permissionName> permissions, bool enabled = true);
```

```nim
proc setPermissions*(this : var WebProcess, permissions : vector[permissionName], enabled : bool = true)
```

**TODO**: `setPermissions` member function

## <a name="setRule"></a> WebProcess::setRule

Set a value to a specified rule for the current web engine

```cpp
void WebProcess::setRule(ruleName rule, int value);
```

```nim
proc setRule*(this : var WebProcess, rule : ruleName, value : cint)
```

**TODO**: `setRule` member function

## <a name="title"></a> WebProcess::title

Get the current page title

```cpp
std::string WebProcess::title(void) const;
```

```nim
proc title*(this : var WebProcess) : string;
```

**TODO**: `title` member function

## <a name="url"></a> WebProcess::url

Get the current page url

```cpp
std::string WebProcess::url(void) const;
```

```nim
proc url*(this : var WebProcess) : string
```

**TODO**: `url` member function documentation

## <a name="WebProcess"></a> WebProcess::WebProcess

Create a new instance of the web engine.

```cpp
WebProcess()
WebProcess(std::string url, std::vector<permissionName> permissions = WebProcess::defaultPermissions())
```

```nim
proc constructWebProcess*() : WebProcess
proc constructWebProcess*(url : string, permissions = defaultPermissions())
```

### Parameters

|Parameter|Description|
|-|-|
|url|The URL of the web page|
|permissions|The list of permissions for the page. See [permissionName]() section for more informations|

## <a name="winId"></a> WebProcess::winId

Get the window indentifier of the rendering area.

```cpp
WId WebProcess::winId();
```

```nim
proc winId*(this : var WebProcess) : WId
```

### WId return type

The `WId` return type is a reimplementation of the native window type for each system. It is generally a system-dependent sized integer. It can be implemented by:

```cpp
typedef unsigned int WId;
```

```nim
type
    WId* = uint
```