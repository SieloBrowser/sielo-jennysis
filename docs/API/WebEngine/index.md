---
title: "WebEngine Namespace"
date: "06/02/2019"
license: "CC-BY-NA"
---

# WebEngine Namespace

The WebProcess namespace provides a lot of object designed to interfacing some
web engine (such as Gecko, Blink or Webkit) and Sielo Core.

## Requirements

### In C++

**Include**: `<WebEngine.hpp>`

**Namespace**: `Sielo::WebEngine`

### In NIM

**Import**: `WebEngine`

## Enums

|Name|Description|
|-|-|
|[httpsStateCode](#httpsStateCode)|List of available https error codes|
|[permissionName](#permissionName)|List of available permissions for a web page|
|[ruleName](#ruleName)|List of available rules for the web engine|

## Objects

|Name|Description|
|-|-|
|[JSInterface](JSInterface.md)|Describe a handler between the javascript engine and the application|
|[NetworkEngine](NetworkEngine.md)|Describe the interface between the network and the web engine|
|[WebDevTools](WebDevTools.md)|Describe the interface between the web engine and the developer tool|
|[WebProcess](WebProcess.md)|Describe the interface between the web engine and the application|

## Structures

|Name|Description|
|-|-|
|[httpsCertificateData](#httpsCertificateData)|Data describing https informations|

## <a name="httpsStateCode"></a> httpsStateCode enum

```cpp
typedef enum httpsStateCode;
```

```nim
type
    httpsStateCode* = enum
```

|Identifier|Description|
|-|-|

## <a name="httpsStateCode"></a> permissionName enum

```cpp
typedef enum permissionName;
```

```nim
type
    permissionName* = enum
```

|Identifier|Description|
|-|-|

## <a name="httpsStateCode"></a> ruleName enum

```cpp
typedef enum ruleName;
```

```nim
type
    ruleName* = enum
```

|Identifier|Description|
|-|-|

## <a name="httpsStateCode"></a> httpsCertificateData struct

```cpp
typedef enum httpsCertificateData;
```

```nim
type
    httpsCertificateData*{.bycopy.} = object
```

|Attribute|Type|Description|
|-|-|-|