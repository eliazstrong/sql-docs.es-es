---
title: Modificación de estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-statistics
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
caps.latest.revision: 9
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: da6db9f8c8538aff80b2e9930354d18b87cb8738
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36196183"
---
# <a name="modify-statistics"></a>Modificar estadísticas
  En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , puede modificar las estadísticas existentes mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **En este tema**  
  
-   **Antes de empezar:**  
  
     [Seguridad](#Security)  
  
-   **Para modificar las estadísticas, use:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permissions  
 Requiere que:  
  
-   El usuario tiene el permiso ALTER en la tabla o la vista.  
  
-   El usuario debe ser el propietario de la tabla o vista indexada o un miembro de uno de los roles siguientes: rol fijo de servidor **sysadmin** , rol fijo de base de datos **db_owner** o rol fijo de base de datos **db_ddladmin** .  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio  
  
#### <a name="to-modify-statistics"></a>Para modificar las estadísticas  
  
1.  En el **Explorador de objetos**, haga clic en el signo más para expandir la base de datos en la que desea modificar una estadística.  
  
2.  Haga clic en el signo más para expandir la carpeta **Tablas** .  
  
3.  Haga clic en el signo más para expandir la tabla en la que desea modificar una estadística.  
  
4.  Haga clic en el signo más para expandir la carpeta **Estadísticas** .  
  
5.  Haga clic con el botón derecho en el objeto de estadísticas que quiera modificar y seleccione **Propiedades**.  
  
6.  En el cuadro de diálogo **Propiedades de estadísticas:** *nombre_estadísticas* , en la página **General** , haga clic en **Agregar**, **Quitar**, **Subir**o **Bajar**o any combination, to alter the properties of the statistics. Recuerde que la ubicación de una columna dentro de la cuadrícula **Columnas de estadísticas** puede afectar considerablemente a la utilidad de las estadísticas.  
  
7.  Haga clic en **Aceptar**.  
  
##  <a name="TsqlProcedure"></a> Usar Transact-SQL  
 **Para modificar las estadísticas**  
  
 Esta tarea no se puede realizar mediante instrucciones Transact-SQL. Para modificar las estadísticas con Transact-SQL, primero debe eliminar la estadística existente y, a continuación, volver a crearla con nuevos atributos.  
  
 Para obtener más información, vea [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) y [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).  
  
  