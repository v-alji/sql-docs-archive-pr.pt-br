---
title: Excluir um grupo de carga de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], delete
- Resource Governor, workload group delete
ms.assetid: d5902c46-5c28-4ac1-8b56-cb4ca2b072d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 801a731db6c5b31bc479d1a3f6079c45ad9a7c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680359"
---
# <a name="delete-a-workload-group"></a><span data-ttu-id="07eaf-102">Excluir um grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="07eaf-102">Delete a Workload Group</span></span>
  <span data-ttu-id="07eaf-103">É possível excluir um grupo de carga de trabalho ou um pool de recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="07eaf-103">You can delete a workload group or resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="07eaf-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="07eaf-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="07eaf-105">**Para excluir um grupo de carga de trabalho usando:**  [Pesquisador de Objetos](#DelWGObjEx), [Propriedades do Resource Governor](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="07eaf-105">**To delete a workload group, using:**  [Object Explorer](#DelWGObjEx), [Resource Governor Properties](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="07eaf-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="07eaf-106">Before You Begin</span></span>  
 <span data-ttu-id="07eaf-107">Não é possível excluir um grupo de carga de trabalho se ele contiver sessões ativas.</span><span class="sxs-lookup"><span data-stu-id="07eaf-107">You cannot delete a workload group if it contains active sessions.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="07eaf-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="07eaf-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="07eaf-109">Se um grupo de cargas de trabalho contiver sessões ativas, a exclusão ou movimentação do grupo de cargas de trabalho para um pool de recursos diferente não terá êxito quando a instrução ALTER RESOURCE GOVERNOR RECONFIGURE for chamada para aplicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="07eaf-109">If a workload group contains active sessions, deleting or moving the workload group to a different resource pool will fail when the ALTER RESOURCE GOVERNOR RECONFIGURE statement is called to apply the change.</span></span> <span data-ttu-id="07eaf-110">Para evitar esse problema, é possível executar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="07eaf-110">To avoid this problem, you can take one of the following actions:</span></span>  
  
-   <span data-ttu-id="07eaf-111">Aguardar até que todas as sessões do grupo afetado sejam desconectadas e depois executar novamente a instrução ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="07eaf-111">Wait until all the sessions from the affected group have disconnected, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
-   <span data-ttu-id="07eaf-112">Interromper explicitamente as sessões do grupo afetado usando o comando KILL e depois executar novamente a instrução ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="07eaf-112">Explicitly stop sessions in the affected group by using the KILL command, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span> <span data-ttu-id="07eaf-113">Se você decidir que não deseja interromper explicitamente as sessões depois de usar **Excluir** , mas antes de interromper as sessões ativas, recrie o grupo usando o nome original e mova o grupo para o pool de recursos original.</span><span class="sxs-lookup"><span data-stu-id="07eaf-113">If you decide that you do not want to explicitly stop sessions after you use **Delete** but before you stop active sessions, re-create the group by using the original name and move the group to the original resource pool.</span></span>  
  
-   <span data-ttu-id="07eaf-114">Reinicie o servidor.</span><span class="sxs-lookup"><span data-stu-id="07eaf-114">Restart the server.</span></span> <span data-ttu-id="07eaf-115">Depois que o processo de reinicialização estiver concluído, o grupo excluído não será criado e um grupo movido usará a atribuição do novo pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="07eaf-115">After the restart process is completed, the deleted group will not be created, and a moved group will use the new resource pool assignment.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="07eaf-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="07eaf-116">Permissions</span></span>  
 <span data-ttu-id="07eaf-117">Excluir um grupo de cargas de trabalho exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="07eaf-117">Deleting a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-workload-group-using-object-explorer"></a><a name="DelWGObjEx"></a> <span data-ttu-id="07eaf-118">Excluir um grupo de cargas de trabalho usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="07eaf-118">Delete a Workload Group Using Object Explorer</span></span>  
 <span data-ttu-id="07eaf-119">**Para excluir um grupo de cargas de trabalho usando o Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="07eaf-119">**To delete a workload group by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="07eaf-120">No[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e inclua o **Pools de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="07eaf-120">In[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="07eaf-121">Expanda recursivamente o nó **Pools de Recursos** para baixo e incluindo o nó **Grupos de Cargas de Trabalho** no pool de recursos que contém o grupo de cargas de trabalho a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="07eaf-121">Recursively expand **Resource Pools** down to and including the **Workload Groups** node in the resource pool that contains the workload group to be deleted.</span></span>  
  
3.  <span data-ttu-id="07eaf-122">Clique com o botão direito do mouse em grupo de cargas de trabalho e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="07eaf-122">Right-click the workload group, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="07eaf-123">Na janela **Excluir Objeto** , o grupo de carga de trabalho é listado em **Objeto a ser excluído** .</span><span class="sxs-lookup"><span data-stu-id="07eaf-123">In the **Delete Object** window, the workload group is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="07eaf-124">Para excluir o grupo de cargas de trabalho, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="07eaf-124">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-resource-governor-properties"></a><a name="DelWGRGProp"></a> <span data-ttu-id="07eaf-125">Excluir um grupo de cargas de trabalho usando propriedades do administrador de recursos</span><span class="sxs-lookup"><span data-stu-id="07eaf-125">Delete a Workload Group Using Resource Governor Properties</span></span>  
 <span data-ttu-id="07eaf-126">**Para excluir um grupo de cargas de trabalho usando a página de propriedades do administrador de recursos**</span><span class="sxs-lookup"><span data-stu-id="07eaf-126">**To delete a workload group by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="07eaf-127">No Pesquisador de Objetos, expanda recursivamente o nó **Gerenciamento** para baixo e incluindo **Pools de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="07eaf-127">In Object Explorer, recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="07eaf-128">Clique com o botão direito do mouse no pool de recursos que contém o grupo de cargas de trabalho a ser excluído e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="07eaf-128">Right-click the resource pool that contains the workload group to be deleted, and then click **Properties**.</span></span> <span data-ttu-id="07eaf-129">Isso abre a página **Propriedades do Administrador de Recursos** .</span><span class="sxs-lookup"><span data-stu-id="07eaf-129">This opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="07eaf-130">Na janela **Grupos de cargas de trabalho para o pool de recursos** , clique na linha do grupo de cargas de trabalho a ser excluído, clique com o botão direito do mouse na seta para a direita no lado esquerdo da linha e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="07eaf-130">In the **Workload groups for resource pool** window, click the line for the workload group to be deleted, then right-click the right arrow on the left side of the line, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="07eaf-131">Para excluir o grupo de cargas de trabalho, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="07eaf-131">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-transact-sql"></a><a name="DelWGTSQL"></a> <span data-ttu-id="07eaf-132">Excluir grupo de cargas de trabalho usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="07eaf-132">Delete a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="07eaf-133">**Para mover um grupo de cargas de trabalho usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="07eaf-133">**To delete a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="07eaf-134">Execute a instrução `DROP WORKLOAD GROUP` especificando o nome do grupo de cargas de trabalho a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="07eaf-134">Run the `DROP WORKLOAD GROUP` statement specifying the name of the workload group to delete.</span></span>  
  
2.  <span data-ttu-id="07eaf-135">Antes de emitir a instrução `ALTER RESOURCE GOVERNOR RECONFIGURE`, verifique se não há solicitações ativas no grupo de cargas de trabalho que está sendo excluído.</span><span class="sxs-lookup"><span data-stu-id="07eaf-135">Before you issue the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement, verify that there are no active requests in the workload group being deleted.</span></span> <span data-ttu-id="07eaf-136">Se houver solicitações ativas, `ALTER RESOURCE GOVERNOR` apresentará falha.</span><span class="sxs-lookup"><span data-stu-id="07eaf-136">If there are active requests, `ALTER RESOURCE GOVERNOR` will fail.</span></span> <span data-ttu-id="07eaf-137">Para evitar esse problema, é possível executar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="07eaf-137">To avoid this issue, you can take one of the following actions:</span></span>  
  
    -   <span data-ttu-id="07eaf-138">Aguarde até que todas as sessões do grupo de carga de trabalho estejam desconectadas.</span><span class="sxs-lookup"><span data-stu-id="07eaf-138">Wait until all the sessions from the workload group have disconnected.</span></span>  
  
    -   <span data-ttu-id="07eaf-139">Explicitamente pare sessões no grupo de cargas de trabalho usando o comando `KILL`.</span><span class="sxs-lookup"><span data-stu-id="07eaf-139">Explicitly stop sessions in the workload group by using the `KILL` command.</span></span>  
  
    -   <span data-ttu-id="07eaf-140">Reinicie o servidor.</span><span class="sxs-lookup"><span data-stu-id="07eaf-140">Restart the server.</span></span> <span data-ttu-id="07eaf-141">O grupo de cargas de trabalho não será recriado.</span><span class="sxs-lookup"><span data-stu-id="07eaf-141">The workload group will not be re-created.</span></span>  
  
    -   <span data-ttu-id="07eaf-142">Em um cenário no qual você emitiu a instrução `DROP WORKLOAD GROUP` mas decide que não deseja parar sessões explicitamente para aplicar a mudança, é possível recriar o grupo usando o mesmo nome que ele tinha antes de você emitir a instrução DROP e depois mover o grupo para o pool de recursos original.</span><span class="sxs-lookup"><span data-stu-id="07eaf-142">In a scenario in which you have issued the `DROP WORKLOAD GROUP` statement but decide that you do not want to explicitly stop sessions to apply the change, you can re-create the group by using the same name that it had before you issued the DROP statement, and then move the group to the original resource pool.</span></span>  
  
3.  <span data-ttu-id="07eaf-143">Execute a `ALTER RESOURCE GOVERNOR RECONFIGURE` instrução.</span><span class="sxs-lookup"><span data-stu-id="07eaf-143">Run the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="07eaf-144">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="07eaf-144">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="07eaf-145">O seguinte exemplo descarta um grupo de carga de trabalho denominado `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="07eaf-145">The following example drops a workload group named `groupAdhoc`.</span></span>  
  
```  
DROP WORKLOAD GROUP groupAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="07eaf-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07eaf-146">See Also</span></span>  
 <span data-ttu-id="07eaf-147">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="07eaf-147">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="07eaf-148">[Criar um pool de recursos](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="07eaf-148">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="07eaf-149">[Criar um grupo de carga de trabalho](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="07eaf-149">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="07eaf-150">[Excluir um pool de recursos](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="07eaf-150">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="07eaf-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="07eaf-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="07eaf-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="07eaf-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="07eaf-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07eaf-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
