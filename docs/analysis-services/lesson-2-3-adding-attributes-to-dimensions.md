---
title: Agregar atributos a dimensiones | Documentos de Microsoft
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 753aad68d1c6fc9fb6fe53efb3b73ae767b4570e
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "34017472"
---
# <a name="lesson-2-3---adding-attributes-to-dimensions"></a>Lección 2: 3: agregar atributos a dimensiones
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

Ahora que ha definido las dimensiones, puede rellenarlas con atributos que representan cada elemento de datos de la dimensión. Los atributos suelen estar basados en campos de una vista del origen de datos. Al agregar atributos a una dimensión, puede incluir campos de cualquier tabla de la vista del origen de datos.  
  
En esta tarea, usará el Diseñador de dimensiones para agregar atributos a las dimensiones Customer y Product. La dimensión Customer incluirá atributos basados en campos de las tablas Customer y Geography.  
  
## <a name="adding-attributes-to-the-customer-dimension"></a>Agregar atributos a la dimensión Customer  
  
#### <a name="to-add-attributes"></a>Para agregar atributos  
  
1.  Abra el Diseñador de dimensiones para la dimensión Customer. Para ello, haga doble clic en la dimensión **Customer** del nodo **Dimensiones** del Explorador de soluciones.  
  
2.  En el panel **Atributos** , observe los atributos Customer Key y Geography Key creados mediante el Asistente para cubos.  
  
3.  En la barra de herramientas de la pestaña **Estructura de dimensión** , asegúrese de que el icono Zoom para ver las tablas del panel **Vista del origen de datos** está establecido al 100 por cien.  
  
4.  Arrastre las columnas siguientes de la tabla **Customer** del panel **Vista del origen de datos** al panel **Atributos** :  
  
    -   **BirthDate**  
  
    -   **MaritalStatus**  
  
    -   **Sexo**  
  
    -   **EmailAddress**  
  
    -   **YearlyIncome**  
  
    -   **TotalChildren**  
  
    -   **NumberChildrenAtHome**  
  
    -   **EnglishEducation**  
  
    -   **EnglishOccupation**  
  
    -   **HouseOwnerFlag**  
  
    -   **NumberCarsOwned**  
  
    -   **Teléfono**  
  
    -   **DateFirstPurchase**  
  
    -   **CommuteDistance**  
  
5.  Arrastre las columnas siguientes de la tabla **Geography** del panel **Vista del origen de datos** al panel **Atributos** :  
  
    -   **Ciudad**  
  
    -   **StateProvinceName**  
  
    -   **SpanishCountryRegionName**  
  
    -   **PostalCode**  
  
6.  En el menú Archivo, haga clic en **Guardar todo**.  
  
## <a name="adding-attributes-to-the-product-dimension"></a>Agregar atributos a la dimensión Product  
  
#### <a name="to-add-attributes"></a>Para agregar atributos  
  
1.  Abra el Diseñador de dimensiones para la dimensión Product. Haga doble clic en la dimensión **Product** en el Explorador de soluciones.  
  
2.  En el panel **Atributos** , observe el atributo Product Key creado mediante el Asistente para cubos.  
  
3.  En la barra de herramientas de la pestaña **Estructura de dimensión** , asegúrese de que el icono Zoom para ver las tablas del panel **Vista del origen de datos** está establecido al 100 por cien.  
  
4.  Arrastre las columnas siguientes de la tabla **Product** del panel **Vista del origen de datos** al panel **Atributos** :  
  
    -   **StandardCost**  
  
    -   **Color**  
  
    -   **SafetyStockLevel**  
  
    -   **ReorderPoint**  
  
    -   **ListPrice**  
  
    -   **Tamaño**  
  
    -   **SizeRange**  
  
    -   **Peso**  
  
    -   **DaysToManufacture**  
  
    -   **ProductLine**  
  
    -   **DealerPrice**  
  
    -   **Clase**  
  
    -   **Estilo**  
  
    -   **ModelName**  
  
    -   **StartDate**  
  
    -   **EndDate**  
  
    -   **Estado**  
  
5.  En el menú Archivo, haga clic en **Guardar todo**.  
  
## <a name="next-task-in-lesson"></a>Siguiente tarea de la lección  
[Revisar las propiedades de dimensión y el cubo](../analysis-services/lesson-2-4-reviewing-cube-and-dimension-properties.md)  
  
## <a name="see-also"></a>Vea también  
[Referencia de propiedades de atributos de dimensión](../analysis-services/multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
  
