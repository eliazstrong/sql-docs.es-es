---
title: IsGeneration (MDX) | Documentos de Microsoft
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: a726470f89f2d3ea1677259e849735a09909a42d
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34740084"
---
# <a name="isgeneration-mdx"></a>IsGeneration (MDX)


  Informa de si un miembro especificado es una generación especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
IsGeneration(Member_Expression, Generation_Number)   
```  
  
## <a name="arguments"></a>Argumentos  
 *Expresión_miembro*  
 Expresión MDX válida que devuelve un miembro.  
  
 *Generation_Number*  
 Expresión numérica válida que especifica la generación con la que se evalúa el miembro especificado.  
  
## <a name="remarks"></a>Notas  
 El **IsGeneration** función devuelve **true** si el miembro especificado está en el número de generación especificado. En caso contrario, la función devuelve **false**. También, si el miembro especificado se evalúa como un miembro vacío, la **IsGeneration** función devuelve **false**.  
  
 Respecto a la indización de la generación, los miembros hoja son el índice 0 de la generación. En el índice de generación, los miembros no hoja se determinan obteniendo primero el índice de generación más alto de la unión de todos los miembros secundarios para el miembro especificado y agregando 1 a ese índice. Debido a la forma en que se determina la indización de la generación de los miembros no hoja, un miembro no hoja específico podría pertenecer a más de una generación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente devuelve TRUE si [Date].[Fiscal].CurrentMember es parte de la segunda generación:  
  
 `WITH MEMBER MEASURES.ISGENERATIONDEMO AS`  
  
 `IsGeneration([Date].[Fiscal].CURRENTMEMBER, 2)`  
  
 `SELECT {MEASURES.ISGENERATIONDEMO} ON 0,`  
  
 `[Date].[Fiscal].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Vea también  
 [Referencia de funciones MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
