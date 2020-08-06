---
title: Criar e gerenciar partições de modelo de tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dab72cf0-95bc-4b63-95dc-505b5cd881c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58c408c712d6ac4b6bd590bd0f8c895dc1a88700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581472"
---
# <a name="create-and-manage-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="647a4-102">Criar e Gerenciar partições de modelos tabulares (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="647a4-102">Create and Manage Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="647a4-103">As partições dividem uma tabela em partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="647a4-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="647a4-104">Cada partição pode ser processada (Atualizada) independentemente de outras partições.</span><span class="sxs-lookup"><span data-stu-id="647a4-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="647a4-105">As partições definidas para um modelo durante a criação de modelo são duplicadas em um modelo implantado.</span><span class="sxs-lookup"><span data-stu-id="647a4-105">Partitions defined for a model during model authoring are duplicated in a deployed model.</span></span> <span data-ttu-id="647a4-106">Uma vez implantado, você pode gerenciar essas partições usando a caixa de diálogo **Partições** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou usando um script.</span><span class="sxs-lookup"><span data-stu-id="647a4-106">Once deployed, you can manage those partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by using a script.</span></span> <span data-ttu-id="647a4-107">As tarefas fornecidas neste tópico descrevem como criar e gerenciar partições para um modelo implantado.</span><span class="sxs-lookup"><span data-stu-id="647a4-107">Tasks provided in this topic describe how to create and manage partitions for a deployed model.</span></span>  
  
 <span data-ttu-id="647a4-108">Este tópico inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="647a4-108">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="647a4-109">Para criar uma nova partição</span><span class="sxs-lookup"><span data-stu-id="647a4-109">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="647a4-110">Para copiar uma partição</span><span class="sxs-lookup"><span data-stu-id="647a4-110">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="647a4-111">Para mesclar duas ou mais partições</span><span class="sxs-lookup"><span data-stu-id="647a4-111">To merge two or more partitions</span></span>](#bkmk_merge)  
  
-   [<span data-ttu-id="647a4-112">Para excluir uma partição</span><span class="sxs-lookup"><span data-stu-id="647a4-112">To delete a partition</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="647a4-113">Tarefas</span><span class="sxs-lookup"><span data-stu-id="647a4-113">Tasks</span></span>  
 <span data-ttu-id="647a4-114">Para criar e gerenciar partições para um banco de dados modelo tabular implantado, você usará a caixa de diálogo **Partições** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="647a4-114">To create and manage partitions for a deployed tabular model database, you will use the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="647a4-115">Para exibir a caixa de diálogo **Gerenciador de Partições** , no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse em uma tabela e clique em **Partições**.</span><span class="sxs-lookup"><span data-stu-id="647a4-115">To view the **Partitions** dialog box, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on a table, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="647a4-116">Para criar uma nova partição</span><span class="sxs-lookup"><span data-stu-id="647a4-116">To create a new partition</span></span>  
  
1.  <span data-ttu-id="647a4-117">Na caixa de diálogo **Partições** , clique no botão **Novo** .</span><span class="sxs-lookup"><span data-stu-id="647a4-117">In the **Partitions** dialog box, click the **New** button.</span></span>  
  
2.  <span data-ttu-id="647a4-118">Em **Nome da Partição**, digite um nome para a partição.</span><span class="sxs-lookup"><span data-stu-id="647a4-118">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="647a4-119">Por padrão, o nome da partição padrão será numerado incrementalmente para cada nova partição.</span><span class="sxs-lookup"><span data-stu-id="647a4-119">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
3.  <span data-ttu-id="647a4-120">Em **Instrução SQL**, digite ou cole uma instrução de consulta SQL que define as colunas e as cláusulas que você quer incluir na partição na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="647a4-120">In **SQL Statement**, type or paste a SQL query statement that defines the columns and any clauses you want to include in the partition into the query window.</span></span>  
  
4.  <span data-ttu-id="647a4-121">Para validar a instrução, clique em **Verificar Sintaxe**.</span><span class="sxs-lookup"><span data-stu-id="647a4-121">To validate the statement, click **Check Syntax**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="647a4-122">Para copiar uma partição</span><span class="sxs-lookup"><span data-stu-id="647a4-122">To copy a partition</span></span>  
  
1.  <span data-ttu-id="647a4-123">Na caixa de diálogo **Partições** , na lista **Partições** , selecione a partição que você deseja copiar e clique em **Copiar** .</span><span class="sxs-lookup"><span data-stu-id="647a4-123">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to copy, and then click the **Copy** button.</span></span>  
  
2.  <span data-ttu-id="647a4-124">Em **Nome da Partição**, digite um novo nome para a partição.</span><span class="sxs-lookup"><span data-stu-id="647a4-124">In **Partition Name**, type a new name for the partition.</span></span>  
  
3.  <span data-ttu-id="647a4-125">Em **Instrução SQL**, edite a instrução de consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="647a4-125">In **SQL Statement**, edit the SQL query statement.</span></span>  
  
###  <a name="to-merge-two-or-more-partitions"></a><a name="bkmk_merge"></a> <span data-ttu-id="647a4-126">Para mesclar duas ou mais partições</span><span class="sxs-lookup"><span data-stu-id="647a4-126">To merge two or more partitions</span></span>  
  
-   <span data-ttu-id="647a4-127">Na caixa de diálogo **Partições** , na lista **Partições** , use Ctrl+click para selecionar as partições que você deseja mesclar e clique em **Mesclar** .</span><span class="sxs-lookup"><span data-stu-id="647a4-127">In the **Partitions** dialog box, in the **Partitions** list, use Ctrl+click to select the partitions you want to merge, and then click the **Merge** button.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="647a4-128">Mesclar partições não atualiza os metadados da partição.</span><span class="sxs-lookup"><span data-stu-id="647a4-128">Merging partitions does not update the partition metadata.</span></span> <span data-ttu-id="647a4-129">Os administradores devem alterar a Instrução SQL para a partição resultante para garantir que as operações de processamento processem todos os dados na partição mesclada.</span><span class="sxs-lookup"><span data-stu-id="647a4-129">Administrators must alter the SQL Statement for the resulting partition to make sure processing operations process all data in the merged partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="647a4-130">Para excluir uma partição</span><span class="sxs-lookup"><span data-stu-id="647a4-130">To delete a partition</span></span>  
  
-   <span data-ttu-id="647a4-131">Na caixa de diálogo **Partições** , na lista **Partições** , selecione a partição que você deseja excluir e clique em **Excluir** .</span><span class="sxs-lookup"><span data-stu-id="647a4-131">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to delete, and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647a4-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="647a4-132">See Also</span></span>  
 <span data-ttu-id="647a4-133">[Partições de modelo de tabela &#40;SSAS de tabela&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="647a4-133">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="647a4-134">Processar partições de modelo de tabela &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="647a4-134">Process Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](process-tabular-model-partitions-ssas-tabular.md)  
  
  
