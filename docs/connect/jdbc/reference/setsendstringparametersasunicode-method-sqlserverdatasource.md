---
title: Método setSendStringParametersAsUnicode (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.setSendStringParametersAsUnicode
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 49198d63-76cb-4843-8d04-e49b1fbb6916
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b630f2bbe44f4484364aa1b99ea987c8888554c1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47637823"
---
# <a name="setsendstringparametersasunicode-method-sqlserverdatasource"></a>Método setSendStringParametersAsUnicode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece un valor **booleano** que indica si está habilitado el envío de parámetros de cadena al servidor en formato UNICODE.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setSendStringParametersAsUnicode(boolean sendStringParametersAsUnicode)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *sendStringParametersAsUnicode*  
  
 **true** si se envían parámetros de cadena al servidor en formato UNICODE. De lo contrario, se devuelve el valor **False**.  
  
## <a name="remarks"></a>Notas  
 Si la propiedad sendStringParametersAsUnicode está configurada en **true**, que es el valor predeterminado, los parámetros de cadena se envían al servidor en formato UNICODE. Si la propiedad sendStringParametersAsUnicode está configurada en **false**, los parámetros de cadena se envían al servidor en formato ASCII/MBCS y no en UNICODE. Si no se establece sendStringParametersAsUnicode, [getSendStringParametersAsUnicode](../../../connect/jdbc/reference/getsendstringparametersasunicode-method-sqlserverdatasource.md) devuelve el valor predeterminado **true**.  
  
 Para obtener más información acerca de la propiedad de conexión sendStringParametersAsUnicode, vea [estableciendo las propiedades de conexión](../../../connect/jdbc/setting-the-connection-properties.md).  
  
## <a name="see-also"></a>Ver también  
 [Miembros SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Clase SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
