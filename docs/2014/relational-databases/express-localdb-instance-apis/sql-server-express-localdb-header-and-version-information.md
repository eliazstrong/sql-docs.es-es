---
title: SQL Server Express LocalDB encabezado e información de versión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: 506b5161-b902-4894-b87b-9192d7b1664a
caps.latest.revision: 12
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e4ba95b47dc6a33d0d943ad224b5be8dde75ea0e
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36197608"
---
# <a name="sql-server-express-localdb-header-and-version-information"></a>Información de encabezado y versión de SQL Server Express LocalDB
  No hay ningún archivo de encabezado independiente para la API de instancia de SQL Server Express LocalDB; las firmas de función y los códigos de error de LocalDB se definen en el archivo de encabezado de SQL Server Native Client (sqlncli.h). Para utilizar la instancia API de LocalDB, debe incluir el archivo de encabezado sqlncli.h en el proyecto.  
  
## <a name="localdb-versioning"></a>Versión de LocalDB  
 La instalación de LocalDB utiliza un conjunto único de archivos binarios por versión principal de SQL Server. Estas versiones de LocalDB se mantienen y se revisan de forma independiente. Esto significa que el usuario tiene que especificar la versión de línea base de LocalDB (es decir, la versión principal de SQL Server) que se va a utilizar. La versión se especifica en el formato de versión estándar definido por .NET Framework **System.Version** clase:  
  
 *principal.secundario]]*  
  
 Los primeros dos números en la cadena de versión (*principal* y *secundaria*) son obligatorios. Los dos últimos números en la cadena de versión (*generar* y *revisión*) son opcionales y el valor de cero si el usuario no los especifica. Esto significa que si el usuario solamente especifica "12.2" como número de versión de LocalDB, se tratará como si el usuario hubiera especificado "12.2.0.0".  
  
 La versión para la instalación de LocalDB se define en la clave del Registro MSSQLServer\CurrentVersion en la clave del Registro de la instancia de SQL Server, por ejemplo:  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12E.LOCALDB\ MSSQLServer\CurrentVersion: "CurrentVersion"="12.0.2531.0"  
```  
  
 Si hay varias versiones de LocalDB en la misma estación de trabajo, se admiten en paralelo. Sin embargo, el código de usuario siempre utiliza la versión más reciente disponible **SQLUserInstance** DLL en el equipo local para conectarse a instancias de LocalDB.  
  
## <a name="locating-the-sqluserinstance-dll"></a>Localizar la DLL de SQLUserInstance  
 Para buscar el **SQLUserInstance** DLL, el proveedor de cliente utiliza la clave del registro siguiente:  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions]  
```  
  
 En esta clave hay una lista de claves, una para cada versión de LocalDB que se haya instalado en el equipo. Cada una de estas claves se denomina con el número de versión de LocalDB con el formato  *\<versión principal >*. *\<menor de versión >* (por ejemplo, la clave para [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] se denomina 12.0). En cada clave de la versión hay un par nombre-valor `InstanceAPIPath` que definen la ruta completa al archivo SQLUserInstance.dll que se haya instalado con esa versión. En el siguiente ejemplo se muestran las entradas del Registro para un equipo con las versiones de LocalDB 11.0 y 12.0 instaladas:  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
```  
  
 El proveedor del cliente debe buscar la última versión entre todas las versiones instaladas y carga el **SQLUserInstance** archivo DLL desde el asociado `InstanceAPIPath` valor.  
  
### <a name="wow64-mode-on-64-bit-windows"></a>Modo WOW64 en Windows de 64 bits  
 Las instalaciones de 64 bits de LocalDB tendrán un conjunto adicional de claves del Registro para que las aplicaciones de 32 bits que se ejecutan en el modo de Windows de 32 bits sobre Windows de 64 bits (WOW64) puedan utilizar LocalDB. Concretamente, en Windows de 64 bits, el MSI de LocalDB creará las claves del Registro siguientes:  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
  
```  
  
 los programas de 64 bits que leen el `Installed Versions` clave verá valores que señalan a las versiones de 64 bits de la **SQLUserInstance** DLL, mientras que los programas de 32 bits (que se ejecutan en Windows de 64 bits en modo WOW64) se redirigirá automáticamente a una `Installed Versions` clave se encuentra en la `Wow6432Node` hive. Esta clave contiene valores que señalan a las versiones de 32 bits de la **SQLUserInstance** DLL.  
  
## <a name="using-localdbdefineproxyfunctions"></a>Uso de LOCALDB_DEFINE_PROXY_FUNCTIONS  
 La API de la instancia de LocalDB define una constante denominada LOCALDB_DEFINE_PROXY_FUNCTIONS que automatiza la detección y la carga de la **SqlUserInstance** DLL.  
  
 La sección de código que se habilita a través de esta constante proporciona una implementación de servidores proxy para cada una de las API de LocalDB. Las implementaciones de proxy usan una función común para enlazar a puntos de entrada en el más reciente instalado **SqlUserInstance** DLL y, a continuación, reenviar las solicitudes.  
  
 Se habilitan las características del servidor proxy únicamente si la constante LOCALDB_DEFINE_PROXY_FUNCTIONS se ha definido en el código de usuario antes de incluir el archivo sqlncli.h. La constante debe estar definida en tan solo un módulo de origen (archivo .cpp) porque define los nombres de función externa para todos los puntos de entrada de la API. Proporciona una implementación de servidores proxy para cada una de las API de LocalDB.  
  
 El ejemplo de código siguiente muestra cómo utilizar la macro a partir de código C++ nativo:  
  
```  
// Define the LOCALDB_DEFINE_PROXY_FUNCTIONS constant to enable the LocalDB proxy functions   
// The #define has to take place BEFORE the API header file (sqlncli.h) is included  
#define LOCALDB_DEFINE_PROXY_FUNCTIONS  
#include <sqlncli.h>  
…  
HRESULT hr = S_OK;  
  
// Create LocalDB instance by calling the create API proxy function included by macro  
if (FAILED(hr = LocalDBCreateInstance( L"12.0", L"name", 0)))  
{  
…  
}  
…  
  
```  
  
  