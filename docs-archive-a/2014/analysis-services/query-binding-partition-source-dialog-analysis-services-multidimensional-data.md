---
title: Detalhes de associação de consulta (caixa de diálogo origem da partição) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitionfilterexpression.f1
ms.assetid: 697874d4-3f7a-4126-96f5-37cc8e2ee306
author: minewiskan
ms.author: owend
ms.openlocfilehash: 59d2ae1fed9d22366786e21a287a621f08418a5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574296"
---
# <a name="query-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="74538-102">Detalhes de Associação de Consulta (caixa de diálogo Origem da Partição) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="74538-102">Query Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="74538-103">Use a opção **Associação de Consulta** na caixa de diálogo **Origem da Partição** para especificar a consulta que fornece os dados para a partição.</span><span class="sxs-lookup"><span data-stu-id="74538-103">Use the **Query Binding** option in the **Partition Source** dialog box to specify the query that provides the data for the partition.</span></span> <span data-ttu-id="74538-104">É possível exibir este painel selecionando **Associação de Consulta** da opção **Tipo de associação** na caixa de diálogo **Origem da Partição** .</span><span class="sxs-lookup"><span data-stu-id="74538-104">You can display this pane by selecting **Query Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74538-105">Opções</span><span class="sxs-lookup"><span data-stu-id="74538-105">Options</span></span>  
 <span data-ttu-id="74538-106">**Fonte de dados**</span><span class="sxs-lookup"><span data-stu-id="74538-106">**Data source**</span></span>  
 <span data-ttu-id="74538-107">Selecione a fonte de dados na qual a consulta é executada para fornecer dados de fato para a partição.</span><span class="sxs-lookup"><span data-stu-id="74538-107">Select the data source on which the query is executed to provide fact data for the partition.</span></span>  
  
 <span data-ttu-id="74538-108">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="74538-108">**Query**</span></span>  
 <span data-ttu-id="74538-109">Digite ou modifique a instrução SQL usada ao recuperar dados de fato quando a partição é processada.</span><span class="sxs-lookup"><span data-stu-id="74538-109">Type or modify the SQL statement used when retrieving fact data when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="74538-110">Ao especificar uma cláusula WHERE, um subconjunto de registros pode ser usado para esta partição.</span><span class="sxs-lookup"><span data-stu-id="74538-110">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="74538-111">Isso é essencial para evitar duplicação de dados quando várias partições estiverem baseadas em uma única tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="74538-111">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span> <span data-ttu-id="74538-112">Para obter mais informações, consulte a [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="74538-112">For more information, see [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="74538-113">**Verificação**</span><span class="sxs-lookup"><span data-stu-id="74538-113">**Check**</span></span>  
 <span data-ttu-id="74538-114">Clique para verificar se a instrução em **Consulta** é uma instrução SQL válida.</span><span class="sxs-lookup"><span data-stu-id="74538-114">Click to verify that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74538-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74538-115">See Also</span></span>  
 [<span data-ttu-id="74538-116">Caixa de diálogo origem da partição &#40;Analysis Services-dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="74538-116">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
