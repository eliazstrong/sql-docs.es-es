---
title: Metadatos (pestaña explorador, Diseñador de cubos) (Analysis Services - datos multidimensionales) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.metadatapane.f1
ms.assetid: a1ace545-488d-4645-8330-56408a5e8abd
caps.latest.revision: 22
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 8469a144844e7b4bb7c02ea7fa5255a04654a34c
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36104353"
---
# <a name="metadata-browser-tab-cube-designer-analysis-services---multidimensional-data"></a>Metadatos (pestaña Explorador, Diseñador de cubos) (Analysis Services - Datos multidimensionales)
  Utilice el panel **Metadatos** en la pestaña **Explorador** del Diseñador de cubos para examinar la estructura del cubo, para ver las medidas relacionadas, y para ver y crear dimensiones. Puede explorar en profundidad las jerarquías, ver una lista de medidas y KPI disponibles, y copiar los nombres completos de objetos.  
  
 También puede arrastrar los objetos y las jerarquías del panel **Metadatos** hasta el área de creación de consultas para crear nuevas consultas o exportar datos para examinarlos en Excel.  
  
## <a name="options"></a>Opciones  
 **Metadatos**  
 Muestra los metadatos disponibles en la vista actual. Puede cambiar la vista (es decir, la perspectiva o el cubo seleccionados actualmente) haciendo clic en el icono de cubo y usando después el cuadro de diálogo **Selección de cubo** para elegir un nuevo cubo o una nueva perspectiva. También puede hacer clic en **Grupo de medida**y seleccionar un nuevo grupo de medida en la lista desplegable para filtrar los objetos disponibles en el panel **Metadatos** .  
  
 Arrastre los elementos seleccionados hasta las áreas de filtro, datos, fila o columna del control PivotTable de [!INCLUDE[msCoName](../includes/msconame-md.md)] Office 11.0 en el panel **Informe** para mostrar los datos del elemento seleccionado.  
  
 **Funciones**  
 Muestra una lista de todas las funciones, operadores y constantes que se pueden usar para crear consultas o vistas de datos en el **Explorador**. Para utilizar una función, busque la que desea y arrástrela al área de consulta. La definición de sintaxis se agrega al texto  
  
> [!WARNING]  
>  La lista **Función** no está disponible cuando se trabaja en la vista de diseño gráfica.  
  
 Cuando se trabaja con un modelo tabular, la lista de funciones contiene funciones MDX y funciones DAX. De lo contrario, la lista solo contiene funciones MDX. Un modelo multidimensional no puede usar funciones DAX directamente, aunque puede incluirse una expresión DAX como parte de una definición de objeto.  
  
 Sugerencia: las carpetas que contienen funciones DAX se muestran con todas las letras en mayúsculas. Todas las demás carpetas contienen funciones MDX. Por ejemplo, hay dos carpetas para las funciones estadísticas: **STATISTICAL** contiene las funciones DAX relacionadas.  
  
## <a name="context-menu"></a>Menú contextual  
 Las siguientes opciones están disponibles en el menú contextual que se muestra al hacer clic con el botón derecho en un elemento del panel **Metadatos** :  
  
|Opción|Descripción|  
|------------|-----------------|  
|**Agregar a consulta**|Haga clic para agregar el objeto seleccionado al panel inferior del área de creación de consultas.|  
|**Agregar a filtro**|Haga clic para agregar la dimensión, el atributo, la jerarquía o el nivel seleccionados al área de filtro del **Explorador**.<br /><br /> Nota: Solo se habilitará esta opción si se selecciona una dimensión, un atributo, una jerarquía o un nivel.|  
|**Copiar**|Haga clic para agregar el elemento seleccionado al Portapapeles.<br /><br /> Nota: Esta opción copia el nombre completo del objeto.|  
  
## <a name="see-also"></a>Vea también  
 [Barra de herramientas &#40;pestaña explorador, Diseñador de cubos&#41; &#40;Analysis Services - datos multidimensionales&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md)   
 [Analizar en Excel &#40;pestaña explorador, Diseñador de cubos&#41; &#40;Analysis Services - datos multidimensionales&#41;](analyze-in-excel-browser-cube-designer-analysis-services-multidimensional-data.md)   
 [Consulta y filtro &#40;pestaña explorador, Diseñador de cubos&#41; &#40;Analysis Services - datos multidimensionales&#41;](query-filter-browser-cube-designer-analysis-services-multidimensional-data.md)   
 [Explorador &#40;Diseñador de cubos&#41; &#40;Analysis Services - datos multidimensionales&#41;](browser-cube-designer-analysis-services-multidimensional-data.md)  
  
  