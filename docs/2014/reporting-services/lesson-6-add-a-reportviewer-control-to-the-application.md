---
title: 'Lección 6: Agregar un control ReportViewer a la aplicación | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9492a97-5609-4059-ae76-0fba111d4968
caps.latest.revision: 7
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: 51b08dce6f232bb08fd1d5f41bc1976aaa410331
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36108038"
---
# <a name="lesson-6-add-a-reportviewer-control-to-the-application"></a>Lección 6: agregar un control ReportViewer a la aplicación
  Después de diseñar el informe secundario con el Asistente de informes, el paso siguiente consiste en agregar un control ReportViewer a la aplicación del sitio Web.  
  
### <a name="to-add-a-reportviewer-control-to-the-application"></a>Para agregar un control ReportViewer a la aplicación  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en **Default.aspx**y, a continuación, haga clic en **Diseñador de vistas**.  
  
2.  En el grupo **Extensiones AJAX** , en la ventana **Cuadro de herramientas** , arrastre un control **ScriptManager** a la superficie de diseño.  
  
3.  En el grupo **Reporting** , arrastre un control **ReportViewer** a la superficie de diseño debajo del control **ScriptManager** .  
  
4.  Abra la ventana **Tareas de ReportViewer** haciendo clic en la flecha de la esquina superior derecha de **ReportViewer** .  
  
5.  En el cuadro **Elegir informe** , seleccione el informe primario que creó.  
  
     Al seleccionar un informe, las instancias de los orígenes de datos usados en el informe se crean automáticamente. El código se genera para crear una instancia de cada DataTable (y el contenedor [DataSet](http://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) ). Un control [ObjectDataSource](http://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) se agrega a la superficie de diseño, correspondiente a cada origen de datos utilizado en el informe. Este control de origen de datos se configura automáticamente.  
  
     Si utiliza Microsoft Visual Studio 2012, asegúrese de que el control ObjectDataSource está enlazado a DataSet1 que esta completo con el espacio de nombres del proyecto, si el nombre completo se muestra en el cuadro de lista desplegable de **Elegir un objeto comercial** (por ejemplo, Projectnamespace.DataSet1TableAdapters.ProductTableAdapter). Tiene acceso al cuadro de lista haciendo clic con el botón secundario en ObjectDataSource y, después, haciendo clic en **Configurar origen de datos**.  
  
6.  En el menú Compilar, haga clic en Compilar sitio Web.  
  
     Se compila el informe y errores como un error de sintaxis en una expresión de informe aparecen en el área de **Lista de errores** . Haga clic en **Lista de errores** en la parte inferior de la ventana de Visual Studio para mostrar el área de **Lista de errores** .  
  
## <a name="next-task"></a>Tarea siguiente  
 Ha agregado correctamente un control ReportViewer a la aplicación del sitio Web. Después, agregará una acción de obtención de detalles en el informe primario.  
  
  