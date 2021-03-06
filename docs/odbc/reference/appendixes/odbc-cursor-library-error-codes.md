---
title: Códigos de Error de biblioteca de cursores ODBC | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- cursor library [ODBC], error codes
- error codes [ODBC], cursor library
- ODBC cursor library [ODBC], error codes
ms.assetid: 9713480e-8744-4f37-a630-20871590d4a1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1fb077261eda4b2e013abd6d87e894637a29216a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47691133"
---
# <a name="odbc-cursor-library-error-codes"></a>Códigos de error de la biblioteca de cursores ODBC
> [!IMPORTANT]  
>  Esta característica se quitará en una versión futura de Microsoft Data Access Components. Evite usar esta característica en nuevos trabajos de desarrollo y piense en modificar las aplicaciones que actualmente utilizan esta característica. En su lugar, utilice los cursores de servidor y el controlador.  
  
 La biblioteca de cursores ODBC devuelve el siguientes SQLSTATEs además de los enumerados en [referencia de la API de ODBC](../../../odbc/reference/syntax/odbc-api-reference.md).  
  
> [!NOTE]  
>  La biblioteca de cursores no ordena los registros de estado; el Administrador de controladores y ODBC 3. *x* controladores son responsables de registros de estado de ordenación.  
  
|SQLSTATE|Descripción|Pueden devolverse desde|  
|--------------|-----------------|--------------------------|  
|01000|Cursor no es actualizable.|**SQLFetch**<br /><br /> **SQLFetchScroll**|  
|01000|No utilizada la biblioteca de cursores. Error de carga.|**SQLBrowseConnect**<br /><br /> **SQLConnect**<br /><br /> **SQLDriverConnect**|  
|01000|No utilizada la biblioteca de cursores. Soporte de controlador insuficiente.|**SQLBrowseConnect**<br /><br /> **SQLConnect**<br /><br /> **SQLDriverConnect**|  
|01000|No utilizada la biblioteca de cursores. Discrepancia de versiones con el Administrador de controladores.|**SQLBrowseConnect**<br /><br /> **SQLConnect**<br /><br /> **SQLDriverConnect**|  
|01000|Controlador devuelve SQL_SUCCESS_WITH_INFO. Se ha perdido el mensaje de advertencia.|**SQLFetch**<br /><br /> **SQLFetchScroll**|  
|S1000|Error general: no se puede crear el búfer de archivo.|**SQLFetch**<br /><br /> **SQLFetchScroll**<br /><br /> **SQLGetData**|  
|S1000|Error general: no se puede leer desde el búfer de archivo.|**SQLFetch**<br /><br /> **SQLFetchScroll**<br /><br /> **SQLGetData**|  
|S1000|Error general: no se puede escribir en el búfer de archivo.|**SQLFetch**<br /><br /> **SQLFetchScroll**<br /><br /> **SQLGetData**|  
|S1000|Error general: no se puede cerrar o eliminar el búfer de archivo.|**SQLFreeHandle**<br /><br /> **SQLFreeStmt**|  
|SL001|Solicitud posicionada no se puede realizar porque no hay columnas de búsqueda se enlazaron.|**SQLExecDirect**<br /><br /> **SQLGetData**<br /><br /> **SQLPrepare**|  
|SL002|No se pudo realizar la solicitud posicionada porque se creó el conjunto de resultados por una condición de combinación.|**SQLExecute**<br /><br /> **SQLExecDirect**<br /><br /> **SQLGetData**|  
|SL003|Dependiente búfer supera el tamaño máximo de segmento.|**SQLFetch**<br /><br /> **SQLFetchScroll**|  
|SL004|No se generó el conjunto de resultados por un **seleccione** instrucción.|**SQLGetData**|  
|SL005|**Seleccione** instrucción contiene una cláusula GROUP BY.|**SQLGetData**|  
|SL006|No se admiten las matrices de parámetros con las solicitudes de posición.|**SQLPrepare**<br /><br /> **SQLExecDirect**|  
|SL008|**SQLGetData** no se permite en un cursor de solo avance (sin almacenamiento en búfer).|**SQLGetData**|  
|SL009|No se enlazaron columnas antes de llamar a **SQLFetch** o **SQLFetchScroll**.|**SQLFetch**<br /><br /> **SQLFetchScroll**|  
|SL010|**SQLBindCol** devuelve SQL_ERROR durante un intento de enlazar a un búfer interno.|**SQLFetch**<br /><br /> **SQLFetchScroll**<br /><br /> **SQLGetData**|  
|SL011|La opción de instrucción es válida sólo después de llamar a **SQLFetch** o **SQLFetchScroll**.|**SQLGetStmtAttr**|  
|SL012|Enlaces de instrucción no se pueden cambiar mientras el cursor está abierto.|**SQLBindCol**<br /><br /> **SQLFreeHandle**<br /><br /> **SQLFreeStmt**<br /><br /> **SQLSetStmtAttr**|  
|SL014|Se ha emitido una solicitud de posición y no todos los campos de número de columna se almacenan en búfer.|**SQLExecDirect**<br /><br /> **SQLExecute**<br /><br /> **SQLPrepare**|  
|SL015|**SQLFetch** y **SQLFetchScroll** no se pueden mezclar.|**SQLExtendedFetch**<br /><br /> **SQLFetch**<br /><br /> **SQLFetchScroll**|
