---
title: Criar consultas de detalhamento usando DMX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42c896ee-e5ee-4017-b66e-31d1fe66d369
author: minewiskan
ms.author: owend
ms.openlocfilehash: 618732bfe48f7b1fe777f7841d686b07877d10ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576063"
---
# <a name="create-drillthrough-queries-using-dmx"></a><span data-ttu-id="81194-102">Criar consultas de detalhamento usando DMX</span><span class="sxs-lookup"><span data-stu-id="81194-102">Create Drillthrough Queries using DMX</span></span>
  <span data-ttu-id="81194-103">Em todos os modelos com suporte ao detalhamento, você pode recuperar dados de caso e dados de estrutura criando uma consulta DMX no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou qualquer outro cliente que ofereça suporte a DMX.</span><span class="sxs-lookup"><span data-stu-id="81194-103">For all models that support drillthrough, you can retrieve case data and structure data by creating a DMX query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any other client that supports DMX.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="81194-104">Para exibir os dados, o detalhamento precisa estar habilitado e você precisa ter as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="81194-104">To view the data, drillthrough must have been enabled, and you must have the necessary permissions.</span></span>  
  
## <a name="specifying-drillthrough-options"></a><span data-ttu-id="81194-105">Especificando opções de detalhamento</span><span class="sxs-lookup"><span data-stu-id="81194-105">Specifying Drillthrough Options</span></span>  
 <span data-ttu-id="81194-106">A sintaxe geral é para recuperar casos de modelo e de estrutura como se segue:</span><span class="sxs-lookup"><span data-stu-id="81194-106">The general syntax is for retrieving model cases and structure cases is as follows:</span></span>  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 <span data-ttu-id="81194-107">Para obter mais informações sobre como usar consultas DMX para retornar dados de caso, consulte [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) e [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span><span class="sxs-lookup"><span data-stu-id="81194-107">For additional information about using DMX queries to return case data, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) and [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="81194-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="81194-108">Examples</span></span>  
 <span data-ttu-id="81194-109">A consulta DMX a seguir retorna os dados de caso para uma série de produtos específica, de um modelo de série temporal.</span><span class="sxs-lookup"><span data-stu-id="81194-109">The following DMX query returns the case data for a specific product series, from a time series model.</span></span> <span data-ttu-id="81194-110">A consulta também retorna a coluna `Amount`, que não foi usada no modelo, mas está disponível na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="81194-110">The query also returns the column `Amount`, which was not used in the model but is available in the mining structure.</span></span>  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 <span data-ttu-id="81194-111">Note que, neste exemplo, um alias foi usado para renomear a coluna de estrutura.</span><span class="sxs-lookup"><span data-stu-id="81194-111">Note that in this example, an alias has been used to rename the structure column.</span></span> <span data-ttu-id="81194-112">Se você não atribuir um alias à coluna de estrutura, a coluna será retornada com o nome 'Expression'.</span><span class="sxs-lookup"><span data-stu-id="81194-112">If you do not assign an alias to the structure column, the column is returned with the name 'Expression'.</span></span> <span data-ttu-id="81194-113">Este é o comportamento padrão para todas as colunas sem nome.</span><span class="sxs-lookup"><span data-stu-id="81194-113">This is the default behavior for all unnamed columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81194-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81194-114">See Also</span></span>  
 <span data-ttu-id="81194-115">[Consultas de detalhamento &#40;mineração de dados&#41;](drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="81194-115">[Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="81194-116">Detalhamento em estruturas de mineração</span><span class="sxs-lookup"><span data-stu-id="81194-116">Drillthrough on Mining Structures</span></span>](drillthrough-on-mining-structures.md)  
  
  
