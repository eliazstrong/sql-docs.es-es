---
title: Clase SqlServiceAdvancedProperty | Documentos de Microsoft
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: SqlServiceAdvancedProperty Class
apilocation: sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords: SqlServiceAdvancedProperty class
ms.assetid: a5d06bde-6058-464c-a4aa-444d83f2331f
caps.latest.revision: "32"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: cc15b15084f74c6749c1c3a33b34beadcb82d0a1
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="sqlserviceadvancedproperty-class"></a>Clase SqlServiceAdvancedProperty
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]El [clase SqlServiceAdvancedProperty](../../../relational-databases/wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) representa una propiedad avanzada del servicio al que hace referencia el [clase SqlService](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) objeto.  
  
 El [propiedad AdvancedProperties (clase SqlService)](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/advancedproperties-property-sqlservice-class.md) hace referencia a una matriz de [clase SqlServiceAdvancedProperty](../../../relational-databases/wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) objetos.  
  
 El [iniciar y detener servicios](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx) clase representa propiedades que son únicas para el servicio. Estas propiedades no están en la lista de propiedades que está asociado el [clase SqlService](http://technet.microsoft.com/library/ms186497.aspx) clase. El [clase SqlServiceAdvancedProperty](http://technet.microsoft.com/library/ms182447.aspx) permite la representación de propiedades de cadena, numérico o booleano. Puede utilizar esta clase para ver las propiedades únicas del servicio especificado.  
  
## <a name="see-also"></a>Vea también  
 [Iniciales, detener y pausar servicios](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  