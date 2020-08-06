---
title: Processar dados (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d88f2dc9-2933-4be5-9bf3-48ffbc2d0a1a
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2066cb6d871f43dda719cab3539253db97bfca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685325"
---
# <a name="process-data-ssas-tabular"></a><span data-ttu-id="6d39b-102">Processar dados (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="6d39b-102">Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="6d39b-103">Ao importar dados para um modelo de tabela, no modo Cache, você está capturando um instantâneo desses dados no momento da importação.</span><span class="sxs-lookup"><span data-stu-id="6d39b-103">When you import data into a tabular model, in Cached mode, you are capturing a snapshot of that data at the time of import.</span></span> <span data-ttu-id="6d39b-104">Em alguns casos, esses dados podem nunca serem alterados e não precisam ser atualizados no modelo.</span><span class="sxs-lookup"><span data-stu-id="6d39b-104">In some cases, that data may never change and it does not need to be updated in the model.</span></span> <span data-ttu-id="6d39b-105">Porém, é mais provável que os dados de que você está importando sejam alterados regularmente. Para que seu modelo reflita os dados mais recentes das fontes de dados, é necessário processar (atualizar) os dados e recalcular os dados calculados.</span><span class="sxs-lookup"><span data-stu-id="6d39b-105">However, it is more likely that the data you are importing from changes regularly, and in order for your model to reflect the most recent data from the data sources, it is necessary to process (refresh) the data and re-calculate calculated data.</span></span> <span data-ttu-id="6d39b-106">Para atualizar os dados em seu modelo, você executa uma ação de processo em todas as tabelas, em uma tabela individual, por uma partição, ou por uma conexão da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6d39b-106">To update the data in your model, you perform a process action on all tables, on an individual table, by a partition, or by a data source connection.</span></span>  
  
 <span data-ttu-id="6d39b-107">Ao criar seu projeto de modelo, inicie as ações de processamento manualmente no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d39b-107">When authoring your model project, process actions must be initiated manually in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6d39b-108">Após a implantação de um modelo, as operações de processamento podem ser executadas usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou programadas usando um script.</span><span class="sxs-lookup"><span data-stu-id="6d39b-108">After a model has been deployed, process operations can be performed by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or scheduled by using a script.</span></span> <span data-ttu-id="6d39b-109">As tarefas descritas aqui todas pertencem a ações de processo que você pode fazer durante a criação do modelo no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d39b-109">Tasks described here all pertain to process actions that you can do during model authoring in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6d39b-110">Para obter mais informações sobre ações de processo para um modelo implantado, consulte [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d39b-110">For more information about process actions for a deployed model, see [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6d39b-111">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6d39b-111">Related Tasks</span></span>  
  
|<span data-ttu-id="6d39b-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="6d39b-112">Topic</span></span>|<span data-ttu-id="6d39b-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="6d39b-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6d39b-114">Processando os dados manualmente &#40;SSAS Tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="6d39b-114">Manually Process Data &#40;SSAS Tabular&#41;</span></span>](manually-process-data-ssas-tabular.md)|<span data-ttu-id="6d39b-115">Descreve como processar manualmente dados de workspace modelo.</span><span class="sxs-lookup"><span data-stu-id="6d39b-115">Describes how to manually process model workspace data.</span></span>|  
|[<span data-ttu-id="6d39b-116">Solucionar problemas de dados de processo &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="6d39b-116">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)|<span data-ttu-id="6d39b-117">Descreve como solucionar problemas de operações de processo.</span><span class="sxs-lookup"><span data-stu-id="6d39b-117">Describes how to troubleshoot process operations.</span></span>|  
  
  
