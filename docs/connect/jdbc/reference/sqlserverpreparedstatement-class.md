---
title: Clase SQLServerPreparedStatement | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: a8481c06-fbba-432b-8c69-4f4619c20ad4
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 529f93e136ac2515e13fb69866ff5b570557cd0b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47741273"
---
# <a name="sqlserverpreparedstatement-class"></a>Clase SQLServerPreparedStatement
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Representa la implementación básica de la funcionalidad de la instrucción preparada de JDBC.  
  
 **Paquete:** com.microsoft.sqlserver.jdbc  
  
 **Extiende:** SQLServerStatement  
  
 **Implementa:** [ISQLServerPreparedStatement](../../../connect/jdbc/reference/isqlserverpreparedstatement-interface.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public class SQLServerPreparedStatement  
```  
  
## <a name="remarks"></a>Notas  
 SQLServerPreparedStatement proporciona métodos que permiten especificar parámetros como cualquier tipo Java nativo y muchos tipos de objetos de Java. SQLServerPreparedStatement prepara una instrucción con el procedimiento almacenado **sp_prepare** de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y, después, vuelve a usar el identificador de instrucciones devuelto cada vez que se ejecute la instrucción ulteriormente y, por lo general, se sirve de parámetros diferentes que proporciona el usuario.  
  
 SQLServerPreparedStatement admite el procesamiento por lotes, donde un conjunto de instrucciones preparadas se ejecuta en un ciclo de ida y vuelta en una misma base de datos, para mejorar el rendimiento en tiempo de ejecución.  
  
 Esta clase admite la acción de desencapsular para la clase SQLServerPreparedStatement, la interfaz ISQLServerPreparedStatement, la interfaz java.sql.PreparedStatement y las clases e interfaces que se admite SQLServerStatement para la acción de desencapsular. Para obtener más información, consulte [contenedores e Interfaces](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## <a name="see-also"></a>Ver también  
 [Miembros de SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [Referencia de API del controlador JDBC](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
