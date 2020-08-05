---
title: Criar e gerenciar partições no banco de dados de espaço de trabalho (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.partitionmgr.f1
ms.assetid: 0b3027d6-652b-4eb3-a197-58b25df65218
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3824dd4763e516dc5e8e34a9ec815d3969f4eb79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572212"
---
# <a name="create-and-manage-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="b1381-102">Criar e gerenciar partições no banco de dados de workspace (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="b1381-102">Create and Manage Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="b1381-103">As partições dividem uma tabela em partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="b1381-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="b1381-104">Cada partição pode ser processada (Atualizada) independentemente de ou em paralelo com outras partições.</span><span class="sxs-lookup"><span data-stu-id="b1381-104">Each partition can then be processed (Refreshed) independently or in parallel with other partitions.</span></span> <span data-ttu-id="b1381-105">As partições podem melhorar a escalabilidade e a gerenciabilidade de bancos de dados grandes.</span><span class="sxs-lookup"><span data-stu-id="b1381-105">Partitions can improve scalability and manageability of large databases.</span></span> <span data-ttu-id="b1381-106">Por padrão, cada tabela tem uma partição que inclui todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="b1381-106">By default, each table has one partition that includes all columns.</span></span> <span data-ttu-id="b1381-107">As tarefas neste tópico descrevem como criar e gerenciar partições no banco de dados de espaço de trabalho modelo usando a caixa de diálogo **Gerenciador de partições** no[!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1381-107">Tasks in this topic describe how to create and manage partitions in the model workspace database by using the **Partition Manager** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span></span>  
  
 <span data-ttu-id="b1381-108">Depois que um modelo for implantado em outra instância do Analysis Services, os administradores de banco de dados podem criar e gerenciar partições no modelo (implantado) usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1381-108">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b1381-109">Para obter mais informações, consulte [Criar e gerenciar partições de modelos tabulares &#40;SSAS tabular&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b1381-109">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="b1381-110">Este tópico inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b1381-110">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="b1381-111">Para criar uma nova partição</span><span class="sxs-lookup"><span data-stu-id="b1381-111">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="b1381-112">Para copiar uma partição</span><span class="sxs-lookup"><span data-stu-id="b1381-112">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="b1381-113">Para excluir uma partição</span><span class="sxs-lookup"><span data-stu-id="b1381-113">To delete a partition</span></span>](#bkmk_delete)  
  
> [!NOTE]  
>  <span data-ttu-id="b1381-114">Você não pode mesclar partições no banco de dados de workspace modelo usando a caixa de diálogo Gerenciador de Partições.</span><span class="sxs-lookup"><span data-stu-id="b1381-114">You cannot merge partitions in the model workspace database by using the Partition Manager dialog box.</span></span> <span data-ttu-id="b1381-115">As partições só podem ser mescladas em um modelo implantado usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1381-115">Partitions can be merged in a deployed model only by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="b1381-116">Tarefas</span><span class="sxs-lookup"><span data-stu-id="b1381-116">Tasks</span></span>  
 <span data-ttu-id="b1381-117">Para criar e gerenciar partições, você usará a caixa de diálogo **Gerenciador de Partições** .</span><span class="sxs-lookup"><span data-stu-id="b1381-117">To create and manage partitions, you will use the **Partitions Manager** dialog box.</span></span> <span data-ttu-id="b1381-118">Para exibir a caixa de diálogo **Gerenciador de Partições** , no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Tabela** e clique em **Partições**.</span><span class="sxs-lookup"><span data-stu-id="b1381-118">To view the **Partitions Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="b1381-119">Para criar uma nova partição</span><span class="sxs-lookup"><span data-stu-id="b1381-119">To create a new partition</span></span>  
  
1.  <span data-ttu-id="b1381-120">No designer de modelo, selecione a tabela para a qual você deseja definir uma partição.</span><span class="sxs-lookup"><span data-stu-id="b1381-120">In the model designer, select the table for which you want to define a partition.</span></span>  
  
2.  <span data-ttu-id="b1381-121">Clique no menu **Tabela** e clique em **Partições**.</span><span class="sxs-lookup"><span data-stu-id="b1381-121">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="b1381-122">No **Gerenciador de Partições**, na caixa de listagem **Tabela** , verifique ou selecione a tabela que você deseja particionar e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b1381-122">In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="b1381-123">Em **Nome da Partição**, digite um nome para a partição.</span><span class="sxs-lookup"><span data-stu-id="b1381-123">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="b1381-124">Por padrão, o nome da partição padrão será numerado incrementalmente para cada nova partição.</span><span class="sxs-lookup"><span data-stu-id="b1381-124">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
5.  <span data-ttu-id="b1381-125">Você pode selecionar as linhas e as colunas a serem incluídas na partição usando o modo de visualização de Tabela ou usando uma consulta SQL criada usando o modo Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="b1381-125">You can select the rows and columns to be included in the partition by using Table Preview mode or by using a SQL query created using Query Editor mode.</span></span>  
  
     <span data-ttu-id="b1381-126">Para usar o modo de visualização de Tabela (padrão), clique no botão **Visualização de Tabela** no canto superior direito da janela de visualização.</span><span class="sxs-lookup"><span data-stu-id="b1381-126">To use Table Preview mode (default), click the **Table Preview** button near the upper-right corner of the preview window.</span></span> <span data-ttu-id="b1381-127">Selecione as colunas que você quer incluir na partição marcando a caixa de seleção ao lado do nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="b1381-127">Select the columns you want to include in the partition by selecting the checkbox next to the column name.</span></span> <span data-ttu-id="b1381-128">Para filtrar linhas, clique com o botão direito do mouse em um valor de célula e clique em **Filtrar por Valor da Célula Selecionada**.</span><span class="sxs-lookup"><span data-stu-id="b1381-128">To filter rows, right click a cell value, and click **Filter by Selected Cell Value**.</span></span>  
  
     <span data-ttu-id="b1381-129">Para usar uma instrução SQL, clique no botão **Editor de Consultas** no canto superior direito da janela de visualização, e digite ou cole uma instrução de consulta SQL na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="b1381-129">To use a SQL statement, click the **Query Editor** button near the upper-right corner of the preview window, then type or paste a SQL query statement into the query window.</span></span> <span data-ttu-id="b1381-130">Para validar sua instrução, clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="b1381-130">To validate your statement, click **Validate**.</span></span> <span data-ttu-id="b1381-131">Para usar o Designer de Consulta, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="b1381-131">To use the Query Designer, click **Design**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="b1381-132">Para copiar uma partição</span><span class="sxs-lookup"><span data-stu-id="b1381-132">To copy a partition</span></span>  
  
1.  <span data-ttu-id="b1381-133">No **Gerenciador de Partições**, na caixa de listagem **Tabela** , verifique ou selecione a tabela que contém a partição que você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="b1381-133">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.</span></span>  
  
2.  <span data-ttu-id="b1381-134">Na lista **Partições** , selecione a partição que você deseja copiar e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="b1381-134">In the **Partitions** list, select the partition you want to copy and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="b1381-135">Em **Nome da Partição**, digite um novo nome para a partição.</span><span class="sxs-lookup"><span data-stu-id="b1381-135">In **Partition Name**, type a new name for the partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="b1381-136">Para excluir uma partição</span><span class="sxs-lookup"><span data-stu-id="b1381-136">To delete a partition</span></span>  
  
1.  <span data-ttu-id="b1381-137">No **Gerenciador de Partições**, na caixa de listagem **Tabela** , verifique ou selecione a tabela que contém a partição que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="b1381-137">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to delete.</span></span>  
  
2.  <span data-ttu-id="b1381-138">Na lista **Partições** , selecione a partição que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b1381-138">In the **Partitions** list, select the partition you want to delete and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1381-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1381-139">See Also</span></span>  
 <span data-ttu-id="b1381-140">[Partições &#40;SSAS de tabela&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b1381-140">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b1381-141">Processar partições no banco de dados de espaço de trabalho &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="b1381-141">Process Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](process-partitions-in-the-workspace-database-ssas-tabular.md)  
  
  
