---
title: sysssispackages (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sysdtspackages90_TSQL
- sysdtspackages90
dev_langs: TSQL
helpviewer_keywords: sysssispackages system table
ms.assetid: 66155dcd-dcdb-4e33-a242-1625828ad8d2
caps.latest.revision: "43"
author: spelluru
ms.author: spelluru
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5b694a277a235b373f1051878551ccca9537623f
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="sysssispackages-transact-sql"></a>sysssispackages (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contiene una fila por cada paquete que se guarda en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Esta tabla se almacena en la **msdb** base de datos.  
  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|**Nombre**|**sysname**|Identificador único del paquete.|  
|**id**|**uniqueidentifier**|Identificador único global (GUID) del paquete.|  
|**Descripción**|**nvarchar**|Descripción opcional del paquete.|  
|**CREATEDATE**|**datetime**|Fecha de creación del paquete.|  
|**folderId**|**uniqueidentifier**|GUID de la carpeta lógica en la que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] incluye el paquete.|  
|**ownersid**|**varbinary**|Identificador de seguridad único del usuario que creó el paquete.|  
|**packagedata**|**image**|El paquete.|  
|**packageformat**|**int**|Formato con el que se guarda el paquete:<br /><br /> Un valor de 2 indica que el paquete se guarda en el [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] formato.<br /><br /> Un valor de 3 indica que el paquete se guarda en formato de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]o una versión posterior.|  
|**PackageType**|**int**|Cliente que creó el paquete. Los valores posibles son los siguientes:<br /><br /> 0 (valor predeterminado)<br /><br /> 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de importación y exportación de asistente)<br /><br /> 3 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replicación)<br /><br /> 5 ([!INCLUDE[ssIS](../../includes/ssis-md.md)] diseñador)<br /><br /> 6 (Asistente o Diseñador de planes de mantenimiento).<br /><br /> <br /><br /> Tenga en cuenta que los valores de esta columna se corresponden con los <xref:Microsoft.SqlServer.Dts.Runtime.DTSPackageType> enumeración.|  
|**VerMajor**|**int**|Última versión importante del paquete.|  
|**VerMinor**|**int**|Última versión de menor importancia del paquete.|  
|**verbuild**|**int**|Última versión de compilación del paquete.|  
|**vercomments**|**nvarchar**|Comentarios acerca de la versión del paquete.|  
|**Verid**|**uniqueidentifier**|El GUID de la versión del paquete.|  
|**IsEncrypted**|**bit**|Valor booleano que indica si el paquete está cifrado.|  
|**readrolesid**|**varbinary**|Rol de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que puede cargar paquetes.|  
|**writerolesid**|**varbinary**|Rol de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que puede guardar paquetes.|  
  
## <a name="see-also"></a>Vea también  
 [Paquetes de Integration Services &#40;SSIS&#41;](../../integration-services/integration-services-ssis-packages.md)  
  
  