---
title: Función SQLGetConnectOption | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLGetConnectOption
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLGetConnectOption
helpviewer_keywords:
- SQLGetConnectOption function [ODBC]
ms.assetid: 59cde899-7957-4b5e-8677-f34d3b859bfd
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 30d91302161b236cee5634196bea33f61411f046
ms.sourcegitcommit: 6443f9a281904af93f0f5b78760b1c68901b7b8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53206154"
---
# <a name="sqlgetconnectoption-function"></a>Función SQLGetConnectOption
**Conformidad**  
 Versión de introducción: Cumplimiento de estándares 1.0 de ODBC: Obsoleto  
  
 **Resumen**  
 En ODBC 3 *.x*, el 2 de ODBC *.x* función **SQLGetConnectOption** ha sido reemplazado por **SQLGetConnectAttr**. Para obtener más información, consulte [SQLGetConnectAttr](../../../odbc/reference/syntax/sqlgetconnectattr-function.md).  
  
> [!NOTE]
>  Para obtener más información sobre lo que el Administrador de controladores se asigna esta función cuando un ODBC 2 *.x* aplicación funciona con una aplicación ODBC 3 *.x* controladores, consulte [asignación de funciones en desuso](../../../odbc/reference/appendixes/mapping-deprecated-functions.md)en el apéndice G: Directrices de controlador para la compatibilidad con versiones anteriores.  
> 
> [!NOTE]
>  No admite el atributo SQL_ASYNC_DBC_FUNCTION_ENABLE introducidas en ODBC 3.8 **SQLGetConnectOption**. Las aplicaciones que usan la operación asincrónica en un identificador de conexión deben utilizar **SQLGetConnectAttr**.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de la API de ODBC](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [Archivos de encabezado de ODBC](../../../odbc/reference/install/odbc-header-files.md)
