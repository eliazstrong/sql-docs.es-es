---
title: "Qué hace el Administrador de controladores | Documentos de Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- driver manager [ODBC], backward compatibility
- compatibility [ODBC], driver manager
- ODBC driver manager [ODBC]
- backward compatibility [ODBC], driver manager
ms.assetid: 57f65c38-d9ee-46c8-9051-128224a582c6
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 64c6fb04fe5c5c693da4982e1c12194bc7e42f98
ms.contentlocale: es-es
ms.lasthandoff: 09/09/2017

---
# <a name="what-the-driver-manager-does"></a>Lo que hace el Administrador de controladores
La tabla siguiente resume cómo ODBC 3*.x* el Administrador de controladores asigna las llamadas a API ODBC 2.* x* mientras que ODBC 3*.x* controladores.  
  
|Función o<br /><br /> atributo de instrucción|Comentarios|  
|-----------------------------------------|--------------|  
|SQL_ATTR_FETCH_BOOKMARK_PTR|Señala el marcador que se va a usar con **SQLFetchScroll**. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación establece este en una API ODBC 2. *x* controlador ODBC 3*.x* el Administrador de controladores lo almacena en caché. Desreferencia el puntero y pasa el valor a la API ODBC 2. *x* controlador en el *FetchOffset* argumento de **SQLExtendedFetch** cuando **SQLFetchScroll** más adelante se llama a la aplicación.<br />-Cuando una aplicación establece este en una aplicación ODBC 3*.x* controlador ODBC 3*.x* el Administrador de controladores pasa la llamada al controlador.|  
|SQL_ATTR_ROW_STATUS_PTR|Apunta a la matriz de Estados de fila se rellena por **SQLFetch**, **SQLFetchScroll**, **SQLBulkOperations**, y **SQLSetPos**. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación establece este en una API ODBC 2. *x* controlador ODBC 3*.x* el Administrador de controladores se almacena en memoria caché su valor. Este valor pasa a la API ODBC 2. *x* controlador en el *RowStatusArray* argumento de **SQLExtendedFetch** cuando **SQLFetchScroll** o **SQLFetch** se llama.<br />-Cuando una aplicación establece este en una aplicación ODBC 3*.x* controlador ODBC 3*.x* el Administrador de controladores pasa la llamada al controlador.<br />-En estado S6, si una aplicación establece SQL_ATTR_ROW_STATUS_PTR y, a continuación, se llama **SQLBulkOperations** (con un *operación* de SQL_ADD) o **SQLSetPos** sin antes de llamar a **SQLFetch** o **SQLFetchScroll**, SQLSTATE HY011 (atributo no se puede establecer ahora) se devuelve.|  
|SQL_ATTR_ROWS_FETCHED_PTR|Señala al búfer en el que **SQLFetch** y **SQLFetchScroll** devuelve el número de filas recuperadas. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación establece este en una API ODBC 2. *x* controlador ODBC 3*.x* el Administrador de controladores se almacena en memoria caché su valor. Este valor pasa a la API ODBC 2. *x* controlador en el *RowCountPtr* argumento de **SQLExtendedFetch** cuando **SQLFetch** o **SQLFetchScroll** llama a la aplicación.<br />-Cuando una aplicación establece este en una aplicación ODBC 3*.x* controlador ODBC 3*.x* el Administrador de controladores pasa la llamada al controlador.|  
|SQL_ATTR_ROW_ARRAY_SIZE|Establece el tamaño del conjunto de filas. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación establece este en una API ODBC 2. *x* controlador ODBC 3*.x* el Administrador de controladores se asigna al atributo de instrucción SQL_ROWSET_SIZE.<br />-Cuando una aplicación establece este en una aplicación ODBC 3*.x* controlador ODBC 3*.x* el Administrador de controladores pasa la llamada al controlador.<br />-Cuando una aplicación trabaja con una aplicación ODBC 3*.x* controlador llama **SQLSetScrollOptions**, SQL_ROWSET_SIZE se establece en el valor de la *RowsetSize* argumento si subyacente el controlador no admite **SQLSetScrollOptions**.|  
|SQL_ROWSET_SIZE|Establece el tamaño del conjunto de filas usado por **SQLExtendedFetch** cuando **SQLExtendedFetch** llama a una API ODBC 2*.x* aplicación. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación establece esto, ODBC 3*.x* el Administrador de controladores pasa la llamada al controlador, independientemente de la versión del controlador.<br />-Cuando una aplicación trabaja con una API ODBC 2. *x* controlador llama **SQLSetScrollOptions**, SQL_ROWSET_SIZE se establece en el valor de la **RowsetSize** argumento.|  
|**SQLBulkOperations**|Realiza una inserción operación o update, delete o fetch por operaciones de marcador. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación llama **SQLBulkOperations** con una *operación* de SQL_ADD en una API ODBC 2.* x* controlador ODBC 3*.x* lo asigna el Administrador de controladores **SQLSetPos** con una *operación* de SQL_ADD.<br />-Cuando se trabaja con una API ODBC 2. *x* controlador que no es compatible con **SQLSetPos** con una *operación* de SQL_ADD, ODBC 3*.x* el Administrador de controladores no se asigna **SQLSetPos** con una *operación* de SQL_ADD a **SQLBulkOperations** con una *operación* de SQL_ADD. Esto es porque **SQLBulkOperations** no se puede llamar en estado S7, qué en ODBC 2.* x* era el único estado en el que **SQLSetPos** se podría llamar.<br />-Si la aplicación llama a **SQLBulkOperations** con una *operación* de SQL_ADD en una API ODBC 2.* x* controlador antes de llamar a **SQLFetchScroll**, ODBC 3*.x* el Administrador de controladores devuelve un error.|  
|**SQLExtendedFetch**|Devuelve el conjunto de filas especificado. Salvo la restricción solo se indique lo contrario, el 3 de ODBC*.x* el Administrador de controladores pasa las llamadas a **SQLExtendedFetch** al controlador, independientemente de la versión del controlador.|  
|**SQLFetch**|Devuelve el siguiente conjunto de filas. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación llama **SQLFetch** en una API ODBC 2.* x* controlador ODBC 3*.x* lo asigna el Administrador de controladores **SQLExtendedFetch**. El *FetchOrientation* argumento de **SQLExtendedFetch** está establecido en SQL_FETCH_NEXT. El Administrador de controladores utiliza el valor almacenado en caché del atributo de instrucción SQL_ATTR_ROW_STATUS_PTR para el *RowStatusArray* argumento y el valor almacenado en caché del atributo de instrucción SQL_ATTR_ROWS_FETCHED_PTR para el * RowCountPtr* argumento.<br />-Una aplicación ODBC 3*.x* aplicación puede mezclar llamadas a **SQLFetch** y **SQLFetchScroll** en una API ODBC 2.* x* controlador porque ODBC 3*.x* asigna el Administrador de controladores **SQLFetch** a **SQLExtendedFetch** cuando una aplicación llama en una API ODBC 2.* x* controlador.<br />-Si está un ODBC 2. *x* controlador no admite **SQLExtendedFetch**, ODBC 3*.x* el Administrador de controladores no se asigna **SQLFetch** o ** SQLFetchScroll** a **SQLExtendedFetch** cuando una aplicación llama en ese controlador. Si la aplicación intenta Establezca SQL_ATTR_ROW_ARRAY_SIZE en un valor mayor que 1, SQLSTATE HYC00 (característica opcional no implementada) se devuelve.<br />-Excepto para las restricciones solo se indique lo contrario, el 3 de ODBC*.x* el Administrador de controladores pasa las llamadas a **SQLFetch** al controlador, independientemente de la versión del controlador.|  
|**SQLFetchScroll**|Devuelve el conjunto de filas especificado. Éstos son los detalles de implementación:<br /><br /> -Cuando una aplicación llama **SQLFetchScroll** en una API ODBC 2.* x* controlador ODBC 3*.x* lo asigna el Administrador de controladores **SQLExtendedFetch**. Usa el valor almacenado en caché del atributo de instrucción SQL_ATTR_ROW_STATUS_PTR para el *RowStatusArray* argumento y el valor almacenado en caché del atributo de instrucción SQL_ATTR_ROWS_FETCHED_PTR para el *RowCountPtr* argumento. Si el *FetchOrientation* argumento en **SQLFetchScroll** es SQL_FETCH_BOOKMARK, usa el valor almacenado en caché de un atributo de instrucción SQL_ATTR_FETCH_BOOKMARK_PTR de la *FetchOffset * argumento y devuelve un error si la *FetchOffset* argumento de **SQLFetchScroll** es no en 0.<br />-Cuando una aplicación llama a esto en una aplicación ODBC 3*.x* controlador ODBC 3*.x* el Administrador de controladores pasa la llamada al controlador.|  
|**SQLSetPos**|Lleva a cabo diversas operaciones por posición. ODBC 3*.x* el Administrador de controladores pasa las llamadas a **SQLSetPos** al controlador, independientemente de la versión del controlador.|  
|**SQLSetScrollOptions**|Cuando se asigna el Administrador de controladores **SQLSetScrollOptions** para una aplicación que trabaja con una aplicación ODBC 3*.x* controlador que no es compatible con **SQLSetScrollOptions**, el controlador El administrador establece la opción de instrucción SQL_ROWSET_SIZE, no el atributo de instrucción de SQL_ATTR_ROW_ARRAY_SIZE, para la *RowsetSize* argumento en **SQLSetScrollOption**. Como resultado, **SQLSetScrollOptions** no se puede usar una aplicación al capturar varias filas mediante una llamada a **SQLFetch** o **SQLFetchScroll**. Se puede utilizar solo cuando se captura varias filas mediante una llamada a **SQLExtendedFetch**.|