---
title: Inicializar suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
caps.latest.revision: 23
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: faf970f260b83fcf8b4d8ce4f42b8aef4bd7b3c2
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36111547"
---
# <a name="initialize-subscriptions"></a>Inicializar suscripciones
  Deberá inicializar los suscriptores antes de que puedan comenzar a recibir datos replicados. No se requiere un conjunto de datos inicial, pero el suscriptor deberá poseer al menos el esquema de cada objeto replicado y todas las tablas de metadatos y los procedimientos necesarios para la replicación.  
  
## <a name="options"></a>Opciones  
 **Propiedades de la suscripción**  
 Active la casilla de la columna **Inicializar** para cada suscriptor que necesite un conjunto de datos inicial. Si desactiva la casilla, solo se inicializarán los procedimientos y metadatos de replicación. Para más información, vea [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md) (Inicializar una suscripción transaccional sin una instantánea).  
  
 Seleccione **Inmediatamente** en la columna **Inicializar cuando** del cuadro de lista desplegable para que el Agente de mezcla o el Agente de distribución transfieran los archivos de instantáneas al suscriptor una vez finalizado el asistente. Seleccione **En la primera sincronización** para que el agente transfiera los archivos la próxima vez que esté programado para ejecutarse. La opción **Inmediatamente** no está disponible para suscripciones de extracción a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]. El Agente de mezcla y el Agente de distribución no se ejecutarán con instancias de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], por lo que deberá inicializar la suscripción de otra forma.  
  
> [!NOTE]  
>  El asistente podría solicitar una conexión al distribuidor para iniciar un trabajo adecuado del Agente de distribución o el Agente de mezcla.  
  
## <a name="see-also"></a>Vea también  
 [Create a Pull Subscription](create-a-pull-subscription.md)   
 [Create a Push Subscription](create-a-push-subscription.md)   
 [Inicializar una suscripción](initialize-a-subscription.md)   
 [Suscribirse a publicaciones](subscribe-to-publications.md)  
  
  