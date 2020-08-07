---
title: Aviso sobre o uso do lado do cliente de GEOMETRY, geography e HIERARCHYid | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 500ee6b3-2154-45d2-a3cf-8760166d9413
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 66898aa056800c0a7573b5afa73762785706ff7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573411"
---
# <a name="warning-about-client-side-usage-of-geometry-geography-and-hierarchyid"></a><span data-ttu-id="ddc1b-102">Aviso sobre uso no lado do cliente de GEOMETRY, GEOGRAPHY e HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="ddc1b-102">Warning about client side usage of GEOMETRY, GEOGRAPHY and HIERARCHYID</span></span>
  <span data-ttu-id="ddc1b-103">O assembly **Microsoft.SqlServer.Types.dll**, que contém os tipos de dados espaciais, foi atualizado da versão 10,0 para a versão 11,0.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-103">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="ddc1b-104">Aplicativos personalizados que referenciam esse assembly poderão falhar quando certas condições forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-104">Custom applications that reference this assembly may fail when certain conditions are true.</span></span>  
  
## <a name="component"></a><span data-ttu-id="ddc1b-105">Componente</span><span class="sxs-lookup"><span data-stu-id="ddc1b-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ddc1b-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="ddc1b-106">Description</span></span>  
 <span data-ttu-id="ddc1b-107">O assembly **Microsoft.SqlServer.Types.dll**, que contém os tipos de dados espaciais, foi atualizado da versão 10,0 para a versão 11,0.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-107">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="ddc1b-108">Aplicativos personalizados que referenciam esse assembly poderão falhar quando as condições a seguir forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-108">Custom applications that reference this assembly may fail when the following conditions are true.</span></span>  
  
-   <span data-ttu-id="ddc1b-109">Quando você move um aplicativo personalizado de um computador no qual [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] o foi instalado em um computador no qual [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] o só está instalado, o aplicativo falhará porque a versão referenciada 10,0 do assembly **SqlTypes** não está presente.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-109">When you move a custom application from a computer on which [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] was installed to a computer on which only [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is installed, the application will fail because the referenced version 10.0 of the **SqlTypes** assembly is not present.</span></span> <span data-ttu-id="ddc1b-110">Talvez você receba esta mensagem de erro: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span><span class="sxs-lookup"><span data-stu-id="ddc1b-110">You may see this error message: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span></span>  
  
-   <span data-ttu-id="ddc1b-111">Quando você faz referência à versão 11,0 do assembly **SqlTypes** e a versão 10,0 também está instalada, essa mensagem de erro pode ser exibida:`"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span><span class="sxs-lookup"><span data-stu-id="ddc1b-111">When you reference the **SqlTypes** assembly version 11.0, and version 10.0 is also installed, you may see this error message: `"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span></span>  
  
-   <span data-ttu-id="ddc1b-112">Quando você faz referência à versão 11,0 do assembly **SqlTypes** de um aplicativo personalizado que tem como alvo o .net 3,5, 4 ou 4,5, o aplicativo falhará, pois o SqlClient por Design carrega a versão 10,0 do assembly.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-112">When you reference the **SqlTypes** assembly version 11.0 from a custom application that targets .NET 3.5, 4, or 4.5, the application will fail because SqlClient by design loads version 10.0 of the assembly.</span></span> <span data-ttu-id="ddc1b-113">Essa falha ocorre quando o aplicativo chama um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="ddc1b-113">This failure occurs when the application calls one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ddc1b-114">O método `GetValue` da classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="ddc1b-114">`GetValue` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="ddc1b-115">O método `GetValues` da classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="ddc1b-115">`GetValues` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="ddc1b-116">operador de índice de colchete [] da classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="ddc1b-116">bracket index operator [] of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="ddc1b-117">O método `ExecuteScalar` da classe `SqlCommand`</span><span class="sxs-lookup"><span data-stu-id="ddc1b-117">`ExecuteScalar` method of the `SqlCommand` class</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="ddc1b-118">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="ddc1b-118">Corrective Action</span></span>  
 <span data-ttu-id="ddc1b-119">Você pode contornar esse problema usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="ddc1b-119">You can work around this issue by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="ddc1b-120">Você pode contornar esse problema no seu código chamando o método `GetSqlBytes`, em vez dos métodos Get listados acima, para recuperar tipos de sistema CLR do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="ddc1b-120">You can work around this issue in your code by calling the `GetSqlBytes` method, instead of the Get methods listed above, to retrieve CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system types, as shown in the following example:</span></span>  
  
    ```csharp  
    string query = "SELECT [SpatialColumn] FROM [SpatialTable]";  
          using (SqlConnection conn = new SqlConnection("..."))  
          {  
                SqlCommand cmd = new SqlCommand(query, conn);  
  
                conn.Open();  
                SqlDataReader reader = cmd.ExecuteReader();  
  
                while (reader.Read())  
                {  
                      // In version 11.0 only  
                      SqlGeometry g =   
    SqlGeometry.Deserialize(reader.GetSqlBytes(0));  
  
                      // In version 10.0 or 11.0  
                      SqlGeometry g2 = new SqlGeometry();  
                      g.Read(new BinaryReader(reader.GetSqlBytes(0).Stream));  
                }  
          }  
    ```  
  
-   <span data-ttu-id="ddc1b-121">Você pode contornar esse problema usando redirecionamento de assembly no arquivo de configuração de aplicativo, conforme mostrado no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="ddc1b-121">You can work around this issue by using assembly redirection in the application configuration file, as shown in the following example:</span></span>  
  
    ```xml  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
        ...  
        <dependentAssembly>  
            <assemblyIdentity name="Microsoft.SqlServer.Types" publicKeyToken="89845dcd8080cc91" culture="neutral" />  
            <bindingRedirect oldVersion="10.0.0.0" newVersion="11.0.0.0" />  
        </dependentAssembly>  
        ...  
    </assemblyBinding>  
    ```  
  
-   <span data-ttu-id="ddc1b-122">Você pode contornar esse problema na sua cadeia de conexão especificando um valor "SQL Server 2012" para o atributo "Type System Version" para forçar o SqlClient a carregar a versão 11.0 do assembly.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-122">You can work around this issue in your connection string by specifying a value of "SQL Server 2012" for the "Type System Version" attribute to force SqlClient to load version 11.0 of the assembly.</span></span> <span data-ttu-id="ddc1b-123">Esse atributo de cadeia de conexão está disponível apenas no .NET 4.5 e versões superiores.</span><span class="sxs-lookup"><span data-stu-id="ddc1b-123">This connection string attribute is available only in .NET 4.5 and above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc1b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ddc1b-124">See Also</span></span>  
 <span data-ttu-id="ddc1b-125">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="ddc1b-125">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="ddc1b-126">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="ddc1b-126">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md
)  
  
  
