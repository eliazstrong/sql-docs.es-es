---
title: Permisos de entidad de seguridad de servidor GRANT (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- impersonate [SQL Server], granting
- granting permissions [SQL Server], logins
- permissions [SQL Server], impersonate
- permissions [SQL Server], logins
- GRANT statement, impersonation
- GRANT statement, logins
- logins [SQL Server], granting access
- granting permissions [SQL Server], impersonation
ms.assetid: 4cbed281-5e1e-4d8b-b410-4c18a6cd0205
caps.latest.revision: 31
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: ee77fb0aa9ddcb274b1ac3ff88690d9675d2d192
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="grant-server-principal-permissions-transact-sql"></a>GRANT (permisos de entidad de seguridad de servidor de Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Concede permisos para un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
GRANT permission [ ,...n ] }   
    ON   
    { [ LOGIN :: SQL_Server_login ]  
      | [ SERVER ROLE :: server_role ] }   
    TO <server_principal> [ ,...n ]  
    [ WITH GRANT OPTION ]  
    [ AS SQL_Server_login ]   
  
<server_principal> ::=   
    SQL_Server_login  
    | SQL_Server_login_from_Windows_login   
    | SQL_Server_login_from_certificate   
    | SQL_Server_login_from_AsymKey   
    | server_role  
```  
  
## <a name="arguments"></a>Argumentos  
 *permiso*  
 Especifica un permiso que puede concederse para un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para obtener una lista de permisos, vea la sección Comentarios que se muestra posteriormente en este tema.  
  
 Inicio de sesión **::** *SQL_Server_login*  
 Especifica el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el que se va a conceder el permiso. El calificador de ámbito (**::**) es necesario.  
  
 ROL de servidor **::** *server_role*  
 Especifica el rol del servidor definido por el usuario en el que se concede el permiso. El calificador de ámbito (**::**) es necesario.  
  
 PARA \<entidadseguridadservidor > especifica los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rol de servidor o de inicio de sesión a la que se va a conceder el permiso.  
  
 *SQL_Server_login*  
 Especifica el nombre de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 *SQL_Server_login_from_Windows_login*  
 Especifica el nombre de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creado desde un inicio de sesión de Windows.  
  
 *SQL_Server_login_from_certificate*  
 Especifica el nombre de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asignado a un certificado.  
  
 *SQL_Server_login_from_AsymKey*  
 Especifica el nombre de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asignado a una clave asimétrica.  
  
 *server_role*  
 Especifica el nombre de un rol de servidor definido por el usuario.  
  
 WITH GRANT OPTION  
 Indica que la entidad de seguridad también podrá conceder el permiso especificado a otras entidades de seguridad.  
  
 AS *SQL_Server_login*  
 Especifica el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del que la entidad de seguridad que ejecuta esta consulta deriva su derecho de conceder el permiso.  
  
## <a name="remarks"></a>Comentarios  
 Los permisos del ámbito del servidor solamente pueden concederse si la base de datos actual es maestra.  
  
 Información acerca de los permisos de servidor está visible en el [sys.server_permissions](../../relational-databases/system-catalog-views/sys-server-permissions-transact-sql.md) vista de catálogo. Información acerca de las entidades de seguridad de servidor está visible en el [sys.server_principals](../../relational-databases/system-catalog-views/sys-server-principals-transact-sql.md) vista de catálogo.  
  
 Los roles de servidor y los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] son protegibles en el nivel de servidor. La mayoría de permisos limitados y específicos que se pueden conceder para un rol de servidor o inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se muestran en la siguiente tabla, junto con permisos más generales que los incluyen por implicación.  
  
|Permiso de rol de servidor o de inicio de sesión de SQL Server|Permiso de rol de servidor o inicio de sesión implícito de SQL Server|Implícito en el permiso de servidor|  
|------------------------------------------------|-----------------------------------------------------------|----------------------------------|  
|CONTROL|CONTROL|CONTROL SERVER|  
|IMPERSONATE|CONTROL|CONTROL SERVER|  
|VIEW DEFINITION|CONTROL|VIEW ANY DEFINITION|  
|ALTER|CONTROL|ALTER ANY LOGIN<br /><br /> ALTER ANY SERVER ROLE|  
  
## <a name="permissions"></a>Permissions  
 Para los inicios de sesión, se necesita el permiso CONTROL en el inicio de sesión o el permiso ALTER ANY LOGIN en el servidor.  
  
 Para los roles de servidor, se necesita el permiso CONTROL en el rol de servidor o el permiso ALTER ANY SERVER ROLE en el servidor.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-granting-impersonate-permission-on-a-login"></a>A. Conceder el permiso IMPERSONATE para un inicio de sesión  
 El siguiente ejemplo se concede `IMPERSONATE` permiso en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicio de sesión `WanidaBenshoof` a una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicio de sesión creado por el usuario de Windows `AdvWorks\YoonM`.  
  
```  
USE master;  
GRANT IMPERSONATE ON LOGIN::WanidaBenshoof to [AdvWorks\YoonM];  
GO  
```  
  
### <a name="b-granting-view-definition-permission-with-grant-option"></a>B. Conceder el permiso VIEW DEFINITION con GRANT OPTION  
 En el siguiente ejemplo se concede `VIEW DEFINITION` para el inicio de sesión `EricKurjan` de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para el inicio de sesión de `RMeyyappan` de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con `GRANT OPTION`.  
  
```  
USE master;  
GRANT VIEW DEFINITION ON LOGIN::EricKurjan TO RMeyyappan   
    WITH GRANT OPTION;  
GO   
```  
  
### <a name="c-granting-view-definition-permission-on-a-server-role"></a>C. Conceder el permiso VIEW DEFINITION en un rol de servidor  
 En el siguiente ejemplo se concede el permiso `VIEW DEFINITION` en el rol de servidor `Sales` al rol de servidor `Auditors`.  
  
```  
USE master;  
GRANT VIEW DEFINITION ON SERVER ROLE::Sales TO Auditors ;  
GO   
```  
  
## <a name="see-also"></a>Vea también  
 [sys.server_principals &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-principals-transact-sql.md)   
 [sys.server_permissions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-permissions-transact-sql.md)   
 [CREATE LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)   
 [Entidades de seguridad &#40;motor de base de datos&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [Permisos &#40;motor de base de datos&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [Funciones de seguridad &#40;Transact-SQL&#41;](../../t-sql/functions/security-functions-transact-sql.md)   
 [Procedimientos almacenados de seguridad &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)  
  
  

