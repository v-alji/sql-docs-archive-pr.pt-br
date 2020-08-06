---
title: Processar partições no banco de dados de espaço de trabalho (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3a369705-43fa-4961-9045-32e06fbdde33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4a996e90b30794882535327ea3192d7e72818422
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678996"
---
# <a name="process-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="305b2-102">Processar partições no banco de dados de espaço de trabalho (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="305b2-102">Process Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="305b2-103">As partições dividem uma tabela em partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="305b2-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="305b2-104">Cada partição pode ser processada (Atualizada) independentemente de outras partições.</span><span class="sxs-lookup"><span data-stu-id="305b2-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="305b2-105">As tarefas neste tópico descrevem como processar partições no banco de dados de workspace modelo usando a caixa de diálogo **Processar Partições** no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="305b2-105">The tasks in this topic describe how to process partitions in the model workspace database by using the **Process Partitions** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="305b2-106">Depois que um modelo for implantado em outra instância do Analysis Services, os administradores de banco de dados podem criar e gerenciar partições no modelo (implantado) usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], por script ou usando um pacote IS.</span><span class="sxs-lookup"><span data-stu-id="305b2-106">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], by script, or by using an IS package.</span></span> <span data-ttu-id="305b2-107">Para obter mais informações, consulte [Criar e gerenciar partições de modelos tabulares &#40;SSAS tabular&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="305b2-107">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="305b2-108">Para processar uma partição</span><span class="sxs-lookup"><span data-stu-id="305b2-108">To process a partition</span></span>  
  
1.  <span data-ttu-id="305b2-109">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Modelo** , em **Processar** (Atualizar) e em **Processar Partições**.</span><span class="sxs-lookup"><span data-stu-id="305b2-109">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="305b2-110">Na caixa de listagem **Modo** , selecione um dos seguintes modos de processo:</span><span class="sxs-lookup"><span data-stu-id="305b2-110">In the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="305b2-111">Mode</span><span class="sxs-lookup"><span data-stu-id="305b2-111">Mode</span></span>|<span data-ttu-id="305b2-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="305b2-112">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="305b2-113">**Processar Padrão**</span><span class="sxs-lookup"><span data-stu-id="305b2-113">**Process Default**</span></span>|<span data-ttu-id="305b2-114">Detecta o estado de processamento de um objeto de partição e realiza o processamento necessário para passar os objetos de partição não processados ou parcialmente processados para um estado completamente processado.</span><span class="sxs-lookup"><span data-stu-id="305b2-114">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="305b2-115">Os dados para tabelas vazias e partições são carregados; hierarquias, colunas calculadas e relações são criadas ou recriadas.</span><span class="sxs-lookup"><span data-stu-id="305b2-115">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="305b2-116">**Processar Completo**</span><span class="sxs-lookup"><span data-stu-id="305b2-116">**Process Full**</span></span>|<span data-ttu-id="305b2-117">Processa um objeto de partição e todos os objetos que ele contém.</span><span class="sxs-lookup"><span data-stu-id="305b2-117">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="305b2-118">Quando o comando Processar Completo for executado para um objeto que já foi processado, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] removerá todos os dados do objeto e processará o objeto.</span><span class="sxs-lookup"><span data-stu-id="305b2-118">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="305b2-119">Esse tipo de processamento é necessário quando uma alteração estrutural é feita em um objeto.</span><span class="sxs-lookup"><span data-stu-id="305b2-119">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="305b2-120">**Processar dados**</span><span class="sxs-lookup"><span data-stu-id="305b2-120">**Process Data**</span></span>|<span data-ttu-id="305b2-121">Carregue os dados em uma partição ou uma tabela sem recriar hierarquias ou relações ou recalcular colunas calculadas e medidas.</span><span class="sxs-lookup"><span data-stu-id="305b2-121">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="305b2-122">**Processar Limpeza**</span><span class="sxs-lookup"><span data-stu-id="305b2-122">**Process Clear**</span></span>|<span data-ttu-id="305b2-123">Remove todos os dados de uma partição.</span><span class="sxs-lookup"><span data-stu-id="305b2-123">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="305b2-124">**Processar adição**</span><span class="sxs-lookup"><span data-stu-id="305b2-124">**Process Add**</span></span>|<span data-ttu-id="305b2-125">Atualize a partição incrementalmente com novos dados.</span><span class="sxs-lookup"><span data-stu-id="305b2-125">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="305b2-126">Na coluna da caixa de seleção **Processar** , selecione as partições que você deseja processar com o modo selecionado e clique em **Ok**.</span><span class="sxs-lookup"><span data-stu-id="305b2-126">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305b2-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="305b2-127">See Also</span></span>  
 <span data-ttu-id="305b2-128">[Partições &#40;SSAS de tabela&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="305b2-128">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="305b2-129">Criar e gerenciar partições no banco de dados de workspace &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="305b2-129">Create and Manage Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](workspace-database-ssas-tabular.md)  
  
  
