---
title: Mover um grupo de carga de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties_moveworkloadgroup.f1
helpviewer_keywords:
- workload groups [SQL Server], move
- Resource Governor, workload group move
ms.assetid: f2068636-6e53-486a-a6fc-c12de2a38424
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f73b48f0ec2255760b4ee55acfaf91dc02af7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680350"
---
# <a name="move-a-workload-group"></a><span data-ttu-id="0ad96-102">Mover um Grupo de Cargas de Trabalho</span><span class="sxs-lookup"><span data-stu-id="0ad96-102">Move a Workload Group</span></span>
  <span data-ttu-id="0ad96-103">Você pode mover um grupo de cargas de trabalho do Administrador de Recursos para um pool de recursos diferente usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0ad96-103">You can move a Resource Governor workload group to a different resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="0ad96-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="0ad96-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="0ad96-105">**Para mover um grupo de cargas de trabalho usando:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="0ad96-105">**To move a workload group, using:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0ad96-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0ad96-106">Before You Begin</span></span>  
 <span data-ttu-id="0ad96-107">Você não pode mover um grupo de cargas de trabalho se houver uma operação de configuração do Administrador de Recursos pendente.</span><span class="sxs-lookup"><span data-stu-id="0ad96-107">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="0ad96-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="0ad96-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="0ad96-109">Você não pode mover um grupo de cargas de trabalho se houver uma operação de configuração do Administrador de Recursos pendente.</span><span class="sxs-lookup"><span data-stu-id="0ad96-109">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span> <span data-ttu-id="0ad96-110">É possível determinar se há uma configuração pendente consultando a exibição de gerenciamento dinâmico de [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) para obter o status atual de is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="0ad96-110">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0ad96-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="0ad96-111">Permissions</span></span>  
 <span data-ttu-id="0ad96-112">Mover um grupo de cargas de trabalho exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="0ad96-112">Moving a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="move-a-workload-group-using-sql-server-management-studio"></a><a name="MoveWGSSMS"></a> <span data-ttu-id="0ad96-113">Mover um grupo de cargas de trabalho usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0ad96-113">Move a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="0ad96-114">**Para mover um grupo de cargas de trabalho usando o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="0ad96-114">**To move a workload group by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span></span>  
  
1.  <span data-ttu-id="0ad96-115">No Pesquisador de Objetos, expanda recursivamente o nó **Gerenciamento** para baixo para o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="0ad96-115">In Object Explorer, recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="0ad96-116">Clique com o botão direito do mouse em **Administrador de Recursos** e clique em **Propriedades**, para abrir a página **Propriedades do Administrador de Recursos** .</span><span class="sxs-lookup"><span data-stu-id="0ad96-116">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="0ad96-117">Na janela **Pools de recursos** , clique no pool de recursos que contém o grupo de cargas de trabalho a ser movido.</span><span class="sxs-lookup"><span data-stu-id="0ad96-117">In the **Resource Pools** window, click the resource pool containing the workload group to be moved.</span></span> <span data-ttu-id="0ad96-118">A janela **Grupos de Cargas de Trabalho** agora lista os grupos de cargas de trabalho nesse pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="0ad96-118">The **Workload Groups** window now lists the workload groups in that resource pool.</span></span>  
  
4.  <span data-ttu-id="0ad96-119">Na janela **Grupos de Cargas de trabalho** , clique com o botão direito do mouse na seta para a direita à esquerda do grupo de cargas de trabalho a ser movido e clique em **Mover para**.</span><span class="sxs-lookup"><span data-stu-id="0ad96-119">In the **Workload Groups** window, right-click the right arrow to the left of the workload group to be moved, and click **Move to**.</span></span> <span data-ttu-id="0ad96-120">Isto exibe uma janela **Mover Grupo de Cargas de Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="0ad96-120">This displays a **Move Workload Group** window.</span></span>  
  
5.  <span data-ttu-id="0ad96-121">Os pools de recursos disponíveis são exibidos na janela.</span><span class="sxs-lookup"><span data-stu-id="0ad96-121">Available resource pools are displayed in the window.</span></span> <span data-ttu-id="0ad96-122">Clique no nome do pool de recursos para o qual deseja mover seu grupo de cargas de trabalho e, depois, clique em **OK** para realizar essa ação.</span><span class="sxs-lookup"><span data-stu-id="0ad96-122">Click the name of the resource pool that you want to move the workload group to, and then click **OK** to carry out this action.</span></span>  
  
6.  <span data-ttu-id="0ad96-123">Essa ação só é completada depois de você clicar em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ad96-123">This action is not completed until after you click **OK**.</span></span> <span data-ttu-id="0ad96-124">Ao clicar em **OK**, a instrução ALTER RESOURCE GOVERNOR RECONFIGURE é executada.</span><span class="sxs-lookup"><span data-stu-id="0ad96-124">When you click **OK**, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
7.  <span data-ttu-id="0ad96-125">Se a operação de criação ou reconfiguração falhar para o pool de recursos ou grupo de cargas de trabalho, um resumo de uma mensagem de erro será exibido abaixo do título da página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="0ad96-125">If the create or reconfigure operation fails for the resource pool or workload group, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="0ad96-126">Para visualizar uma mensagem de erro detalhada, clique na seta para baixo na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="0ad96-126">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
##  <a name="move-a-workload-group-using-transact-sql"></a><a name="MoveWGTSQL"></a> <span data-ttu-id="0ad96-127">Mover grupo de cargas de trabalho usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ad96-127">Move a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="0ad96-128">**Para mover um grupo de cargas de trabalho usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="0ad96-128">**To move a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="0ad96-129">Execute a instrução `ALTER WORKLOAD GROUP` que especifica o nome do grupo de cargas de trabalho a ser movido e o pool de recursos para o qual ele deve ser movido.</span><span class="sxs-lookup"><span data-stu-id="0ad96-129">Run the `ALTER WORKLOAD GROUP` statement specifying the name of the workload group to be moved and the resource pool to which it should be moved.</span></span>  
  
2.  <span data-ttu-id="0ad96-130">Execute a instrução **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="0ad96-130">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="0ad96-131">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0ad96-131">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="0ad96-132">O exemplo a seguir move um grupo de cargas de trabalho chamado `groupAdhoc` para o pool de recursos padrão.</span><span class="sxs-lookup"><span data-stu-id="0ad96-132">The following example moves a workload group named `groupAdhoc` to the default resource pool.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
USING [default];  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ad96-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ad96-133">See Also</span></span>  
 <span data-ttu-id="0ad96-134">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="0ad96-134">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="0ad96-135">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="0ad96-135">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="0ad96-136">[Criar um pool de recursos](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="0ad96-136">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="0ad96-137">[Criar um grupo de carga de trabalho](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="0ad96-137">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="0ad96-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ad96-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="0ad96-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ad96-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
