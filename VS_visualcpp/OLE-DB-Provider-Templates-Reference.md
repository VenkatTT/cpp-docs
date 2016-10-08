---
title: "OLE DB Provider Templates Reference"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: 6
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# OLE DB Provider Templates Reference
The classes and interfaces for the OLE DB Provider Templates can be grouped into the following categories. The reference material also includes information about the [macros for OLE DB Provider Templates](../VS_visualcpp/Macros-for-OLE-DB-Provider-Templates.md).  
  
 The classes use the following naming convention: a class named with the pattern **IWidgetImpl** would provide an implementation of the interface **IWidget**.  
  
## Session Classes  
 [IDBCreateSessionImpl](../VS_visualcpp/IDBCreateSessionImpl-Class.md)  
 Creates a new session from the data source object and returns the requested interface on the newly created session. Mandatory interface on data source objects.  
  
 [ISessionPropertiesImpl](../VS_visualcpp/ISessionPropertiesImpl-Class.md)  
 Implements session properties by calling a static function defined by the property set map. The property set map should be specified in your session class. Mandatory interface on sessions.  
  
## Rowset Classes  
 [CRowsetImpl](../VS_visualcpp/CRowsetImpl-Class.md)  
  
 Provides a standard OLE DB rowset implementation without requiring multiple inheritance of many implementation interfaces. The only method for which you must provide implementation is **Execute**.  
  
 [CSimpleRow](../VS_visualcpp/CSimpleRow-Class.md)  
 Provides a default implementation for the row handle, which is used in the `IRowsetImpl` class. A row handle is logically a unique tag for a result row. `IRowsetImpl` creates a new `CSimpleRow` for every row requested in `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../VS_visualcpp/IAccessorImpl-Class.md)  
 OLE DB requires providers to implement an **HACCESSOR**, which is a tag to an array of **DBBINDING** structures. Provides **HACCESSOR**s that are addresses of the **BindType** structures. Mandatory on rowsets and commands.  
  
 [IColumnsInfoImpl](../VS_visualcpp/IColumnsInfoImpl-Class.md)  
 Delegates to a static function defined by the provider column map. Mandatory interface on rowsets and commands.  
  
 [IConvertTypeImpl](../VS_visualcpp/IConvertTypeImpl-Class.md)  
 Gives information on the availability of type conversions on a command or on a rowset. Mandatory on commands, rowsets, and index rowsets. Implements the **IConvertType** interface by delegating to the conversion object supplied by OLE DB.  
  
 [IDBSchemaRowsetImpl](../VS_visualcpp/IDBSchemaRowsetImpl-Class.md)  
 Implements the **IDBSchemaRowset** interface and the templatized creator function `CreateSchemaRowset`.  
  
 [IOpenRowsetImpl](../VS_visualcpp/IOpenRowsetImpl-Class.md)  
 Opens and returns a rowset that includes all rows from a single base table or index. Mandatory interface for a session object.  
  
 [IRowsetChangeImpl](../VS_visualcpp/IRowsetChangeImpl-Class.md)  
 Implements the OLE DB [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) interface, which enables updating of the values of columns in existing rows, deleting rows, and inserting new rows.  
  
 [IRowsetCreatorImpl](../VS_visualcpp/IRowsetCreatorImpl-Class.md)  
 This class inherits from [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) and overrides [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). `IRowsetCreatorImpl` performs the same functions as `IObjectWithSite` but also enables the OLE DB properties **DBPROPCANSCROLLBACKWARDS** and **DBPROPCANFETCHBACKWARDS**.  
  
 [IRowsetIdentityImpl](../VS_visualcpp/IRowsetIdentityImpl-Class.md)  
 Implements the **IRowsetIdentity** interface, which allows you to compare whether two rows of data are identical or not.  
  
 [IRowsetImpl](../VS_visualcpp/IRowsetImpl-Class.md)  
 Provides an implementation of the `IRowset` interface, which is the base rowset interface.  
  
 [IRowsetInfoImpl](../VS_visualcpp/IRowsetInfoImpl-Class.md)  
 Implements the rowset properties by using the property set map defined in your command class. Mandatory interface on rowsets.  
  
 [IRowsetLocateImpl](../VS_visualcpp/IRowsetLocateImpl-Class.md)  
 Implements the OLE DB [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) interface, which fetches arbitrary rows from a rowset. To support OLE DB bookmarks in a rowset, make the rowset inherit from this class.  
  
 [IRowsetNotifyCP](../VS_visualcpp/IRowsetNotifyCP-Class.md)  
 Implements broadcast functions to advise listeners on the connection point **IID_IRowsetNotify** of changes to the contents of the rowset. Consumers that handle notifications implement [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) and register it on that connection point.  
  
 [IRowsetUpdateImpl](../VS_visualcpp/IRowsetUpdateImpl-Class.md)  
 Implements the OLE DB [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) interface, which enables consumers to delay the transmission of changes made with [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) to the data source and undo changes before transmission.  
  
## Command Classes  
 [ICommandImpl](../VS_visualcpp/ICommandImpl-Class.md)  
 Provides an implementation of the `ICommand` interface. This interface is not visible, but is handled by **ICommandTextImpl**. A mandatory interface on the command object.  
  
 [ICommandPropertiesImpl](../VS_visualcpp/ICommandPropertiesImpl-Class.md)  
 This implementation of the **ICommandProperties** interface is provided by a static function defined by the `BEGIN_PROPSET_MAP` macro. Mandatory on commands.  
  
 [ICommandTextImpl](../VS_visualcpp/ICommandTextImpl-Class.md)  
 Sets, stores, and returns the command text. Mandatory on commands.  
  
 [IDBCreateCommandImpl](../VS_visualcpp/IDBCreateCommandImpl-Class.md)  
 Creates a new command from the session object and returns the requested interface on the newly created command. Optional interface on session objects.  
  
 Other command classes are `IColumnsInfoImpl` and `IAccessorImpl`, described in the Rowset Classes section above.  
  
## Data Source Classes  
 [IDBInitializeImpl](../VS_visualcpp/IDBInitializeImpl-Class.md)  
 Creates and deletes the connection with the consumer. Mandatory interface on data source objects and optional interface on enumerators.  
  
 [IDBPropertiesImpl](../VS_visualcpp/IDBPropertiesImpl-Class.md)  
 `IDBProperties` is a mandatory interface for data source objects and an optional interface for enumerators. However, if an enumerator exposes **IDBInitialize**, it must expose `IDBProperties` (properties on the data source).  
  
 [IGetDataSourceImpl](../VS_visualcpp/IGetDataSourceImpl-Class.md)  
 Obtains an interface pointer to the data source object. Mandatory interface on the session.  
  
## Other Classes  
 [CUtlProps](../VS_visualcpp/CUtlProps-Class.md)  
 Implements properties for a variety of OLE DB property interfaces (for example, `IDBProperties`, **ISessionProperties**, and `IRowsetInfo`).  
  
 [IErrorRecordsImpl](../VS_visualcpp/IErrorRecordsImpl-Class.md)  
  
 Implements the OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) interface, adding records to and retrieving records from a data member.  
  
## See Also  
 [OLE DB Consumer Templates Reference](../VS_visualcpp/OLE-DB-Consumer-Templates-Reference.md)   
 [OLE DB Templates](../VS_visualcpp/OLE-DB-Templates.md)