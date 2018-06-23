---
title: 'Tutorial: SQL Server Backup and Restore a Windows Azure Blob Storage Service | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e1d94ce-2c93-45d1-ae2a-2a7d1fa094c4
caps.latest.revision: 10
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 85f16d4f3a96c8d661981a998eab93eaffdc67d7
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36204559"
---
# <a name="tutorial-sql-server-backup-and-restore-to-windows-azure-blob-storage-service"></a>Tutorial: copias de seguridad y restauración de SQL Server en el servicio Azure Blob Storage
  Este es el tutorial Introducción a las copias de seguridad y la restauración de SQL Server con el servicio de almacenamiento Blob de Windows Azure. Este tutorial le ayudará a entender cómo escribir copias de seguridad en el servicio almacenamiento Blob de Windows Azure y cómo restaurar desde el mismo.  
  
## <a name="what-you-will-learn"></a>Aprendizaje  
 Este tutorial muestra cómo crear una cuenta de almacenamiento de Windows, un contenedor de blobs, crear credenciales para tener acceso a la cuenta de almacenamiento, escribir una copia de seguridad en el servicio de blob y realizar una restauración simple. El tutorial está compuesto por cuatro lecciones:  
  
 [Lección 1: Crear objetos de almacenamiento de Azure de Windows](../tutorials/lesson-1-create-windows-azure-storage-objects.md)  
 En esta lección, creará una cuenta de almacenamiento de Windows Azure y un contenedor de blobs.  
  
 [Lección 2: Crear una credencial de SQL Server](../tutorials/lesson-2-create-a-sql-server-credential.md)  
 En esta lección, creará una credencial para almacenar la información de seguridad usada para tener acceso a la cuenta de almacenamiento de Windows Azure.  
  
 [Lección 3: Escribir una copia de seguridad completa de la base de datos en el servicio de almacenamiento de blobs de Azure de Windows](../tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md)  
 En esta lección, emitirá una instrucción T-SQL para escribir una copia de seguridad de la base de datos AdventureWorks2012 en el servicio de almacenamiento Blob de Windows Azure.  
  
 [Lección 4: Realizar una restauración desde una copia de seguridad completa de la base de datos](../tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)  
 En esta lección, emitirá una instrucción T-SQL para restaurar desde la copia de seguridad de la base de datos creada en la lección anterior.  
  
### <a name="requirements"></a>Requisitos  
 Para completar este tutorial, debe estar familiarizado con los conceptos de copias de seguridad y restauración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y con la sintaxis de T-SQL. Para usar este tutorial, el sistema debe cumplir los requisitos siguientes:  
  
-   Una instancia de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] y la base de datos AdventureWorks2012 instalada.  
  
     La instancia de SQL Server puede ser local o residir en una máquina virtual de Windows Azure.  
  
     Puede usar una base de datos de usuario en lugar de AdventureWorks2012 y modificar la sintaxis de tsql en consecuencia.  
  
-   La cuenta de usuario que se usa para emitir comandos BACKUP o RESTORE debe tener el rol de base de datos **operador de db_backup** con permisos **Modificar cualquier credencial** .  
  
### <a name="additional-reading"></a>Lecturas adicionales  
 A continuación se indican algunas lecturas recomendadas para entender los conceptos y las prácticas recomendadas cuando se usa el servicio de almacenamiento Blob de Windows Azure para copias de seguridad de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
1.  [SQL Server Backup and Restore with Windows Azure Blob Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
2.  [Prácticas recomendadas y solución de problemas de Copia de seguridad en URL de SQL Server](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
  
  