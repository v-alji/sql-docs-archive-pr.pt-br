---
title: Funcionalidade do servidor ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- functionality [ADOMD.NET]
- ADOMD.NET, functionality
ms.assetid: b74c6957-3f64-4e09-aa09-d06ee93f82fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: f00215c6bcc0104c920be29e0837288a469b252e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679075"
---
# <a name="adomdnet-server-functionality"></a><span data-ttu-id="10560-102">Funcionalidade de servidor do ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="10560-102">ADOMD.NET Server Functionality</span></span>
  <span data-ttu-id="10560-103">Todos os objetos de servidor do ADOMD.NET oferecem acesso somente leitura aos dados e metadados do servidor.</span><span class="sxs-lookup"><span data-stu-id="10560-103">All ADOMD.NET server objects provide read-only access to the data and metadata on the server.</span></span> <span data-ttu-id="10560-104">Para recuperar dados e metadados, use o modelo de objeto de servidor do ADOMD.NET, uma vez que o modelo de objeto de servidor não dá suporte a conjuntos de linhas do esquema.</span><span class="sxs-lookup"><span data-stu-id="10560-104">To retrieve data and metadata, you use the ADOMD.NET server object model as the server object model does not support schema rowsets.</span></span>  
  
 <span data-ttu-id="10560-105">Com os objetos de servidor do ADOMD.NET, você pode criar uma UDF (função definida pelo usuário) ou um procedimento armazenado para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10560-105">With ADOMD.NET server objects, you can create a user defined function (UDF) or a stored procedure for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="10560-106">Estes métodos em processo são chamados por instruções de consulta criadas em linguagens como MDX (Multidimensional Expressions), DMX (Data Mining Extensions) ou SQL.</span><span class="sxs-lookup"><span data-stu-id="10560-106">These in-process methods are called through query statements created in languages such as Multidimensional Expressions (MDX), Data Mining Extensions (DMX), or SQL.</span></span> <span data-ttu-id="10560-107">Esses métodos em processo também oferecem funcionalidade agregada sem as latências associadas às comunicações de rede.</span><span class="sxs-lookup"><span data-stu-id="10560-107">These in-process methods also provide added functionality without the latencies associated with network communications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10560-108">O objeto [Microsoft. AnalysisServices. AdomdServer. AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) só dá suporte ao DMX.</span><span class="sxs-lookup"><span data-stu-id="10560-108">The [Microsoft.AnalysisServices.AdomdServer.AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) object only supports DMX.</span></span>  
  
## <a name="what-is-a-udf"></a><span data-ttu-id="10560-109">O que é um UDF?</span><span class="sxs-lookup"><span data-stu-id="10560-109">What is a UDF?</span></span>  
 <span data-ttu-id="10560-110">Um *UDF* é um método que tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="10560-110">A *UDF* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="10560-111">Você pode chamar o UDF no contexto de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="10560-111">You can call the UDF in the context of a query.</span></span>  
  
-   <span data-ttu-id="10560-112">O UDF pode conter qualquer número de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="10560-112">The UDF can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="10560-113">O UDF pode retornar vários tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="10560-113">The UDF can return various types of data.</span></span>  
  
 <span data-ttu-id="10560-114">O exemplo a seguir usa o UDF fictício `FinalSalesNumber`:</span><span class="sxs-lookup"><span data-stu-id="10560-114">The following example uses the fictional UDF, `FinalSalesNumber`:</span></span>  
  
```  
SELECT SalesPerson.Name ON ROWS,  
       FinalSalesNumber() ON COLUMNS  
FROM SalesModel  
```  
  
## <a name="what-is-a-stored-procedure"></a><span data-ttu-id="10560-115">O que é um procedimento armazenado?</span><span class="sxs-lookup"><span data-stu-id="10560-115">What is a Stored Procedure?</span></span>  
 <span data-ttu-id="10560-116">Um *procedimento armazenado* é um método que tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="10560-116">A *stored procedure* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="10560-117">Você chama um procedimento armazenado por conta própria com a instrução MDX [Call](/sql/mdx/mdx-data-manipulation-call) .</span><span class="sxs-lookup"><span data-stu-id="10560-117">You call a stored procedure on its own with the MDX [CALL](/sql/mdx/mdx-data-manipulation-call) statement.</span></span>  
  
-   <span data-ttu-id="10560-118">Um procedimento armazenado pode conter qualquer número de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="10560-118">A stored procedure can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="10560-119">Um procedimento armazenado pode retornar um conjunto de dados, um `IDataReader` ou um resultado vazio.</span><span class="sxs-lookup"><span data-stu-id="10560-119">A stored procedure can return a dataset, an `IDataReader`, or an empty result.</span></span>  
  
 <span data-ttu-id="10560-120">O exemplo a seguir usa o procedimento armazenado fictício `FinalSalesNumbers`:</span><span class="sxs-lookup"><span data-stu-id="10560-120">The following example uses the fictional stored procedure, `FinalSalesNumbers`:</span></span>  
  
```  
CALL FinalSalesNumbers()  
```  
  
## <a name="see-also"></a><span data-ttu-id="10560-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10560-121">See Also</span></span>  
 [<span data-ttu-id="10560-122">Programando o servidor no ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="10560-122">ADOMD.NET Server Programming</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-programming)  
  
  
