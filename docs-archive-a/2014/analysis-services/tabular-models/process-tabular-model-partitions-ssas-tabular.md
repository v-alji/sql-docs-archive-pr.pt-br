---
title: Processar partições de modelo de tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6c498d2b-22d6-4661-bc21-2ee708336c8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 496874707bd4030a98b1794fe7513d1d857390ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678993"
---
# <a name="process-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="b3870-102">Processar partições de modelo tabular (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="b3870-102">Process Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="b3870-103">As partições dividem uma tabela em partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="b3870-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="b3870-104">Cada partição pode ser processada (Atualizada) independentemente de outras partições.</span><span class="sxs-lookup"><span data-stu-id="b3870-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="b3870-105">As tarefas neste tópico descrevem como processar partições em um banco de dados modelo usando a caixa de diálogo **Processar Partições** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3870-105">The tasks in this topic describe how to process partitions in a model database by using the **Process Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="b3870-106">Para processar uma partição</span><span class="sxs-lookup"><span data-stu-id="b3870-106">To process a partition</span></span>  
  
1.  <span data-ttu-id="b3870-107">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse na tabela que tem as partições que você deseja processar e clique em **Partições**.</span><span class="sxs-lookup"><span data-stu-id="b3870-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on the table that has the partitions you want to process, and then click **Partitions**.</span></span>  
  
2.  <span data-ttu-id="b3870-108">Na caixa de diálogo **Partições** , em **Partições**, clique no botão Processar.</span><span class="sxs-lookup"><span data-stu-id="b3870-108">In the **Partitions** dialog box, in **Partitions**, click on the Process button.</span></span>  
  
3.  <span data-ttu-id="b3870-109">Na caixa de diálogo **processar partição (s)** , no **modo** de caixa de listagem, selecione um dos seguintes modos de processo:</span><span class="sxs-lookup"><span data-stu-id="b3870-109">In the **Process Partition(s)** dialog box, in the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="b3870-110">Mode</span><span class="sxs-lookup"><span data-stu-id="b3870-110">Mode</span></span>|<span data-ttu-id="b3870-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3870-111">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="b3870-112">**Processar Padrão**</span><span class="sxs-lookup"><span data-stu-id="b3870-112">**Process Default**</span></span>|<span data-ttu-id="b3870-113">Detecta o estado de processamento de um objeto de partição e realiza o processamento necessário para passar os objetos de partição não processados ou parcialmente processados para um estado completamente processado.</span><span class="sxs-lookup"><span data-stu-id="b3870-113">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="b3870-114">Os dados para tabelas vazias e partições são carregados; hierarquias, colunas calculadas e relações são criadas ou recriadas.</span><span class="sxs-lookup"><span data-stu-id="b3870-114">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="b3870-115">**Processar Completo**</span><span class="sxs-lookup"><span data-stu-id="b3870-115">**Process Full**</span></span>|<span data-ttu-id="b3870-116">Processa um objeto de partição e todos os objetos que ele contém.</span><span class="sxs-lookup"><span data-stu-id="b3870-116">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="b3870-117">Quando o comando Processar Completo for executado para um objeto que já foi processado, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] removerá todos os dados do objeto e processará o objeto.</span><span class="sxs-lookup"><span data-stu-id="b3870-117">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="b3870-118">Esse tipo de processamento é necessário quando uma alteração estrutural é feita em um objeto.</span><span class="sxs-lookup"><span data-stu-id="b3870-118">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="b3870-119">**Processar dados**</span><span class="sxs-lookup"><span data-stu-id="b3870-119">**Process Data**</span></span>|<span data-ttu-id="b3870-120">Carregue os dados em uma partição ou uma tabela sem recriar hierarquias ou relações ou recalcular colunas calculadas e medidas.</span><span class="sxs-lookup"><span data-stu-id="b3870-120">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="b3870-121">**Processar Limpeza**</span><span class="sxs-lookup"><span data-stu-id="b3870-121">**Process Clear**</span></span>|<span data-ttu-id="b3870-122">Remove todos os dados de uma partição.</span><span class="sxs-lookup"><span data-stu-id="b3870-122">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="b3870-123">**Processar adição**</span><span class="sxs-lookup"><span data-stu-id="b3870-123">**Process Add**</span></span>|<span data-ttu-id="b3870-124">Atualize a partição incrementalmente com novos dados.</span><span class="sxs-lookup"><span data-stu-id="b3870-124">Incrementally update partition with new data.</span></span>|  
  
4.  <span data-ttu-id="b3870-125">Na coluna da caixa de seleção **Processar** , selecione as partições que você deseja processar com o modo selecionado e clique em **Ok**.</span><span class="sxs-lookup"><span data-stu-id="b3870-125">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3870-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3870-126">See Also</span></span>  
 <span data-ttu-id="b3870-127">[Partições de modelo de tabela &#40;SSAS de tabela&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b3870-127">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b3870-128">Criar e gerenciar partições de modelos de tabela &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="b3870-128">Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](create-and-manage-tabular-model-partitions-ssas-tabular.md)  
  
  
