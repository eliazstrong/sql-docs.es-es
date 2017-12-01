---
title: sp_srvrolepermission (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/20/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_srvrolepermission_TSQL
- sp_srvrolepermission
dev_langs: TSQL
helpviewer_keywords: sp_srvrolepermission
ms.assetid: 5709667f-e3e4-48a2-93ec-af5e22a2ac58
caps.latest.revision: "32"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a2cf4b670588739a7c6232b27bf6a592ef82daaa
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2017
---
# <a name="spsrvrolepermission-transact-sql"></a>sp_srvrolepermission (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Muestra los permisos de un rol de servidor fijo.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_srvrolepermission [ [ @srvrolename = ] 'role']  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@srvrolename =** ] **'***rol***'**  
 Es el nombre del rol fijo de servidor para el que se devuelven permisos. *rol* es **sysname**, su valor predeterminado es null. Si no se especifica un rol, se devuelven los permisos de todos los roles fijos de servidor. *rol* puede tener uno de los siguientes valores.  
  
|Valor|Description|  
|-----------|-----------------|  
|**sysadmin**|Administradores del sistema|  
|**securityadmin**|Administradores de seguridad|  
|**serveradmin**|Administradores de servidor|  
|**setupadmin**|Administradores de instalación|  
|**processadmin**|Administradores de proceso|  
|**diskadmin**|Administradores de disco|  
|**dbcreator**|Creadores de bases de datos|  
|**bulkadmin**|Puede ejecutar instrucciones BULK INSERT|  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nombre de columna|Tipo de datos|Description|  
|-----------------|---------------|-----------------|  
|**ServerRole**|**sysname**|Nombre de un rol fijo de servidor|  
|**Permiso**|**sysname**|Permiso asociado **ServerRole**|  
  
## <a name="remarks"></a>Comentarios  
 Los permisos enumerados incluyen las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que se pueden ejecutar y otras actividades especiales que pueden realizar los miembros del rol fijo de servidor. Para mostrar una lista de los roles fijos de servidor, ejecute **sp_helpsrvrole**.  
  
 El **sysadmin** rol fijo de servidor tiene los permisos de todos los demás roles fijos de servidor.  
  
## <a name="permissions"></a>Permissions  
 Debe pertenecer al rol **public** .  
  
## <a name="examples"></a>Ejemplos  
 En la siguiente consulta se devuelven los permisos asociados al rol fijo de servidor `sysadmin`.  
  
```  
EXEC sp_srvrolepermission 'sysadmin';  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [Seguridad almacena procedimientos &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [sp_addsrvrolemember &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addsrvrolemember-transact-sql.md)   
 [sp_dropsrvrolemember &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-dropsrvrolemember-transact-sql.md)   
 [sp_helpsrvrole &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-helpsrvrole-transact-sql.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  