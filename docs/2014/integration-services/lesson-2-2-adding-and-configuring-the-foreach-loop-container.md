---
title: 'Paso 2: Agregar y configurar el contenedor de bucles Foreach | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 88a973cc-0f23-4ecf-adb6-5b06279c2df6
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2aa42ac9ab25c9765aac2afa10abdd50f2df4cb7
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "53360123"
---
# <a name="step-2-adding-and-configuring-the-foreach-loop-container"></a>Paso 2: Agregar y configurar el contenedor de bucles Foreach
  En esta tarea, agregará la capacidad de buscar en una carpeta de archivos planos y aplicará la misma transformación de flujo de datos utilizada en la lección 1 a cada uno de dichos archivos planos. Para ello, agregará y configurará un contenedor de bucles Foreach para el flujo de control.  
  
 El contenedor de bucles Foreach que agregue debe poder conectarse a cada uno de los archivos planos de la carpeta. Puesto que todos los archivos de la carpeta tienen el mismo formato, el contenedor de bucles Foreach puede utilizar el mismo administrador de conexiones de archivos planos para conectarse a cada uno de estos archivos. El administrador de conexiones de archivos planos que el contenedor utilizará es el mismo administrador de conexiones de archivos planos que creó en la lección 1.  
  
 Actualmente, el administrador de conexiones de archivos planos de la lección 1 se conecta a un único archivo plano específico. Para conectarse de forma iterativa a cada uno de los archivos planos de la carpeta, deberá configurar el contenedor de bucles Foreach y el administrador de conexiones de archivos planos de este modo:  
  
-   **Contenedor de bucles foreach:** Se asignará el valor enumerado del contenedor a una variable de paquete definida por el usuario. El contenedor utilizará esta variable definida por el usuario para modificar de forma dinámica la propiedad `ConnectionString` del administrador de conexiones de archivos planos y conectar de forma iterativa cada uno de los archivos planos de la carpeta.  
  
-   **Administrador de conexiones de archivos planos:** Modificará el Administrador de conexiones que se creó en la lección 1 mediante el uso de una variable definida por el usuario para rellenar el Administrador de conexiones `ConnectionString` propiedad.  
  
 En los procedimientos de esta tarea se muestra cómo crear y modificar el contenedor de bucles Foreach para utilizar una variable de paquete definida por el usuario y agregar la tarea de flujo de datos al bucle. Aprenderá a modificar el administrador de conexiones de archivos planos para utilizar una variable definida por el usuario en la siguiente tarea.  
  
 Una vez realizadas estas modificaciones en el paquete, cuando éste se ejecute, el contenedor de bucles Foreach se iterará en la colección de archivos de la carpeta Datos de ejemplo. Cada vez que se encuentre un archivo que coincida con los criterios, el contenedor de bucles Foreach llenará la variable definida por el usuario con el nombre de archivo, asignará la variable definida por el usuario a la propiedad `ConnectionString` del administrador de conexiones de archivos planos Sample Currency Data y, a continuación, ejecutará el flujo de datos en dicho archivo. Por consiguiente, en cada iteración del bucle Foreach la tarea de flujo de datos utilizará un archivo plano distinto.  
  
> [!NOTE]  
>  Puesto que [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separa el flujo de control del flujo de datos, los bucles que agregue al flujo de control no precisarán ninguna modificación en el flujo de datos. Por consiguiente, no es necesario modificar el flujo de datos creado en la lección 1.  
  
### <a name="to-add-a-foreach-loop-container"></a>Para agregar un contenedor de bucles Foreach  
  
1.  En **SQL Server Data Tools**, haga clic en la pestaña **Flujo de control** .  
  
2.  En el **Cuadro de herramientas de SSIS**, expanda **Contenedores**y arrastre un **Contenedor de bucles Foreach** a la superficie de diseño de la pestaña **Flujo de control** .  
  
3.  Haga clic con el botón derecho en el **Contenedor de bucles Foreach** que acaba de agregar y seleccione **Editar**.  
  
4.  En el **Editor de bucles Foreach** cuadro de diálogo el **General** página, para **nombre**, escriba `Foreach File in Folder`. Haga clic en **Aceptar**.  
  
5.  Haga clic en el contenedor de bucles Foreach, haga clic en **propiedades**y en la ventana Propiedades, compruebe que la `LocaleID` propiedad está establecida en **inglés (Estados Unidos)**.  
  
### <a name="to-configure-the-enumerator-for-the-foreach-loop-container"></a>Para configurar el enumerador para el contenedor de bucles Foreach  
  
1.  Haga doble clic en Foreach File in Folder para volver a abrir el **Editor de bucles Foreach**.  
  
2.  Haga clic en **Colección**.  
  
3.  En la página **Colección** , seleccione **Enumerador de archivos Foreach**.  
  
4.  En el grupo **Configuración de enumerador** , haga clic en **Examinar**.  
  
5.  En el cuadro de diálogo **Buscar carpeta** , busque la carpeta del equipo que contenga los archivos Currency_*.txt.  
  
     Estos datos de ejemplo se incluyen con los paquetes de lecciones de [!INCLUDE[ssIS](../includes/ssis-md.md)] . Para descargar los datos de ejemplo y los paquetes de lecciones, haga lo siguiente.  
  
    1.  Navegue a los [ejemplos del producto Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)  
  
    2.  Haga clic en la pestaña **DOWNLOADS** .  
  
    3.  Haga clic en el hipervínculo "http://msftisprodsamples.codeplex.com/downloads/get/578097" SQL2012. Archivo Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.  
  
6.  En el cuadro **Archivos**, escriba **Currency_\*.txt**.  
  
### <a name="to-map-the-enumerator-to-a-user-defined-variable"></a>Para asignar el enumerador a una variable definida por el usuario  
  
1.  Haga clic en **Asignaciones de variables**.  
  
2.  En la página **Asignaciones de variables**, en la columna **Variable**, haga clic en la celda vacía y seleccione **\<Nueva variable…>**.  
  
3.  En el **agregar Variable** cuadro de diálogo para **nombre**, tipo `varFileName`.  
  
    > [!IMPORTANT]  
    >  Los nombres de variables distinguen entre mayúsculas y minúsculas.  
  
4.  Haga clic en **Aceptar**.  
  
5.  Haga clic de nuevo en **Aceptar** para salir del cuadro de diálogo **Editor de bucles Foreach** .  
  
### <a name="to-add-the-data-flow-task-to-the-loop"></a>Para agregar la tarea de flujo de datos al bucle  
  
-   Arrastre el **Extract Sample Currency Data** tarea de flujo de datos en el contenedor de bucles Foreach que ahora se denomina `Foreach File in Folder`.  
  
## <a name="next-lesson-task"></a>Tarea de la siguiente lección  
 [Paso 3: Modificar el Administrador de conexiones de archivos planos](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
## <a name="see-also"></a>Vea también  
 [Configurar un contenedor de bucles Foreach](control-flow/foreach-loop-container.md)   
 [Usar variables en paquetes](use-variables-in-packages.md)  
  
  
