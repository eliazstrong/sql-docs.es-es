---
title: "Instalación de SSMA para Sybase (SybaseToSQL) | Documentos de Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 8d5a4ce6-b747-46e3-9184-645d56e8b35c
caps.latest.revision: 6
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 432a31ae12c1d3fc091893de332a72a5da1c4fc3
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="installing-ssma--for-sybase-sybasetosql"></a>Instalación de SSMA para Sybase (SybaseToSQL)
[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]Migration Assistant (SSMA) para Sybase consta de una aplicación cliente que se usa para realizar una migración de Sybase Adaptive Server Enterprise (ASE) a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] o SQL Azure. También contiene un módulo de extensión que admite la migración de datos y el uso de funciones del sistema ASE en las bases de datos migrados.  
  
Instale la aplicación cliente en el equipo desde el que se llevará a cabo los pasos de migración. Debe instalar los archivos del módulo de extensión en el equipo que está ejecutando [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] donde se hospedará las bases de datos migradas.  
  
## <a name="upgrading-ssma-for-sybase"></a>Actualización de SSMA para Sybase  
Si desea actualizar a una versión posterior de SSMA para Sybase, debe desinstalar primero el cliente y el módulo de extensión de servidor y, a continuación, instale la versión más reciente.  
  
Si abre un proyecto desde una versión anterior de SSMA para Sybase, SSMA le preguntará si desea convertir el proyecto a la versión más reciente. Debe hacer clic en **Sí** para trabajar con el proyecto en la versión más reciente de SSMA.  
  
## <a name="contents"></a>Contenido  
  
|Tema|Description|  
|---------|---------------|  
|[Instalación de SSMA para Sybase cliente &#40; SybaseToSQL &#41;](../../ssma/sybase/installing-ssma-for-sybase-client-sybasetosql.md)|Proporciona información sobre e instrucciones para instalar al cliente SSMA.|  
|[Instalar componentes SSMA de SQL Server &#40; SybaseToSQL &#41;](../../ssma/sybase/installing-ssma-components-on-sql-server-sybasetosql.md)|Proporciona información sobre e instrucciones para instalar el módulo de extensión en las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].|  
|[Eliminación de SSMA para Sybase componentes &#40; SybaseToSQL &#41;](../../ssma/sybase/removing-ssma-for-sybase-components-sybasetosql.md)|Proporciona instrucciones para desinstalar al cliente de paquete de programa y la extensión.|  
  
## <a name="see-also"></a>Vea también  
[Migrar bases de datos de ASE de Sybase a SQL Server: base de datos de SQL Azure &#40; SybaseToSQL &#41;](../../ssma/sybase/migrating-sybase-ase-databases-to-sql-server-azure-sql-db-sybasetosql.md)  
  
