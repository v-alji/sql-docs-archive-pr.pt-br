---
title: Excluir um pool de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool delete
- resource pools [SQL Server], delete
ms.assetid: 3bdd348b-6582-4ffa-80ef-d49e50596ce5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a67b0e2262fa3007597091b6087cc937bb0f3276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680355"
---
# <a name="delete-a-resource-pool"></a><span data-ttu-id="0339d-102">Excluir um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="0339d-102">Delete a Resource Pool</span></span>
  <span data-ttu-id="0339d-103">É possível excluir um pool de recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0339d-103">You can delete a resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="0339d-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="0339d-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="0339d-105">**Para excluir um pool de recursos usando:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="0339d-105">**To delete a resource pool, using:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0339d-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0339d-106">Before You Begin</span></span>  
 <span data-ttu-id="0339d-107">Não é possível excluir um pool de recursos se ele contiver grupos de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0339d-107">You cannot delete a resource pool if it contains workload groups.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="0339d-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="0339d-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="0339d-109">Você não pode excluir os pools internos ou padrão do Administrador de recursos.</span><span class="sxs-lookup"><span data-stu-id="0339d-109">You cannot delete the Resource Governor default or internal resource pools.</span></span> <span data-ttu-id="0339d-110">Não é possível excluir um pool de recursos se ele contiver grupos de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0339d-110">You cannot delete a resource pool if it contains workload groups.</span></span> <span data-ttu-id="0339d-111">Para obter mais informações, consulte [Delete a Workload Group](delete-a-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="0339d-111">For more information, see [Delete a Workload Group](delete-a-workload-group.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0339d-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="0339d-112">Permissions</span></span>  
 <span data-ttu-id="0339d-113">Excluir um pool de recursos exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="0339d-113">Deleting a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-resource-pool-using-object-explorer"></a><a name="DelRPSSMS"></a> <span data-ttu-id="0339d-114">Excluir um pool de recursos usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="0339d-114">Delete a Resource Pool Using Object Explorer</span></span>  
 <span data-ttu-id="0339d-115">**Para excluir um pool de recursos, usando SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0339d-115">**To delete a resource pool by using SQL Server Management Studio**</span></span>  
  
1.  <span data-ttu-id="0339d-116">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e inclua o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="0339d-116">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="0339d-117">Clique com o botão direito do mouse no pool de recursos a ser excluído e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0339d-117">Right-click the resource pool to be deleted, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="0339d-118">Na janela **Excluir Objeto** , o pool de recursos é exibido na lista **Objeto a ser excluído** .</span><span class="sxs-lookup"><span data-stu-id="0339d-118">In the **Delete Object** window, the resource pool is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="0339d-119">Para excluir o pool de recursos, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0339d-119">To delete the resource pool, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0339d-120">Haverá falha ao tentar excluir um pool de recursos que contém um grupo de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0339d-120">If the resource pool that you are trying to delete contains a workload group, this action will fail.</span></span>  
  
##  <a name="delete-a-resource-pool-using-transact-sql"></a><a name="DelRPTSQL"></a> <span data-ttu-id="0339d-121">Excluir um pool de recursos usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0339d-121">Delete a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="0339d-122">**Para excluir um pool de recursos usando o Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="0339d-122">**To delete a resource pool by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="0339d-123">Execute a instrução `DROP RESOURCE POOL` especificando o nome do pool de recursos a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="0339d-123">Run the `DROP RESOURCE POOL` statement specifying the name of the resource pool to delete.</span></span>  
  
2.  <span data-ttu-id="0339d-124">Execute a instrução **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="0339d-124">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="0339d-125">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0339d-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="0339d-126">O seguinte exemplo descarta um grupo de carga de trabalho denominado `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="0339d-126">The following example drops a workload group named `poolAdhoc`.</span></span>  
  
```  
DROP RESOURCE POOL poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0339d-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0339d-127">See Also</span></span>  
 <span data-ttu-id="0339d-128">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="0339d-128">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="0339d-129">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="0339d-129">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="0339d-130">[Criar um pool de recursos](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="0339d-130">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="0339d-131">[Alterar configurações do pool de recursos](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="0339d-131">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="0339d-132">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="0339d-132">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="0339d-133">[Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="0339d-133">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="0339d-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0339d-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="0339d-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0339d-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="0339d-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0339d-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
