---
title: "Paso 1: Creación de la utilidad de implementación | Documentos de Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 227ebbba4190ff05ebdc04f988beafec4edc8a37
ms.contentlocale: es-es
ms.lasthandoff: 09/26/2017

---
# <a name="lesson-2-1---building-the-deployment-utility"></a>Lección 2-1: creación de la utilidad de implementación
En esta tarea, configurará y generará una utilidad de implementación para el proyecto Deployment Tutorial.  
  
Antes de generar la utilidad de implementación, debe modificar las propiedades del proyecto Deployment Tutorial. Usará el cuadro de diálogo **Deployment Tutorial Property Pages** (Páginas de propiedades de Deployment Tutorial) para configurar estas propiedades. En este cuadro de diálogo, debe habilitar la capacidad de actualizar configuraciones durante la implementación y especificar que el proceso de creación crea una utilidad de implementación. Después de establecer las propiedades, generará el proyecto.  
  
[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] proporciona un conjunto de ventanas que puede usar para depurar paquetes. Puede ver mensajes de errores, advertencias e información, realizar el seguimiento del estado de paquetes en tiempo de ejecución o ver el progreso y los resultados de los procesos de generación. En esta lección, usará la ventana de resultados para ver el progreso y el resultado de la generación de la utilidad de implementación.  
  
### <a name="to-set-the-deployment-utility-properties"></a>Para establecer las propiedades de la utilidad de implementación  
  
1.  Si [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no está abierto todavía, haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server**y, después, haga clic en **Business Intelligence Development Studio**.  
  
2.  En el menú **Archivo** , haga clic en **Abrir**y, en **Proyecto o solución**, haga clic en la carpeta **Deployment Tutorial** a continuación, haga clic en **Abrir**y, después, haga doble clic en **Deployment Tutorial.sln**.  
  
3.  En el Explorador de soluciones, haga clic con el botón derecho en Deployment Tutorial y haga clic en **Propiedades**.  
  
4.  En el cuadro de diálogo **Deployment Tutorial Property Pages** (Páginas de propiedades de Deployment Tutorial), expanda Propiedades de configuración y haga clic en Utilidad de implementación.  
  
5.  En el panel derecho del cuadro de diálogo **Deployment Tutorial Property Pages** (Páginas de propiedades de Deployment Tutorial), compruebe que **AllowConfigurationChanges** se establece en **True**, establezca **CreateDeploymentUtility** en **True**y, de manera opcional, actualice el valor predeterminado de **DeploymentOutputPath**.  
  
6.  Haga clic en **Aceptar**.  
  
### <a name="to-build-the-deployment-utility"></a>Para generar las propiedades de la utilidad de implementación  
  
1.  En el Explorador de soluciones, haga clic en **Deployment Tutorial**.  
  
2.  En el menú **Ver** , haga clic en **Salida**. De forma predeterminada, la ventana de resultados se encuentra en la esquina inferior izquierda de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
3.  En el menú **Generar** , haga clic en **Build Deployment Tutorial**(Generar Deployment Tutorial).  
  
4.  En la ventana de resultados, compruebe la siguiente información:  
  
    Generación iniciada: proyecto de SQL Integration Services: Incremental...  
  
    Creando la utilidad de implementación...  
  
    Utilidad de implementación creada.  
  
    Generación completa -- 0 errores, 0 advertencias  
  
    ========== Compilación: 0 correcto, 0 errores, 1 actualizados, 0 omitidos ==========  
  
5.  En el menú **Archivo** , haga clic en **Salir**. Si se le pregunta si quiere guardar los cambios en los elementos de Deployment Tutorial, haga clic en **Sí**.  
  
## <a name="next-task-in-lesson"></a>Siguiente tarea de la lección  
[Paso 2: Comprobar el paquete de implementación](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
## <a name="see-also"></a>Vea también  
[Crear una utilidad de implementación](../integration-services/packages/create-a-deployment-utility.md)  
  
  
  
