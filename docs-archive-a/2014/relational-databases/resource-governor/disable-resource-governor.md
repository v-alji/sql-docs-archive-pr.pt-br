---
title: Desabilitar Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, disabling
ms.assetid: 2c2d2db0-34a5-4f50-b783-17693e3ce3f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 172f01bdde0f792cd9ed72ad371e5811b8de8885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680354"
---
# <a name="disable-resource-governor"></a><span data-ttu-id="02381-102">Desabilitar Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="02381-102">Disable Resource Governor</span></span>
  <span data-ttu-id="02381-103">Você pode desabilitar o Administrador de Recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="02381-103">You can disable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="02381-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="02381-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="02381-105">**Para desabilitar o Administrador de Recursos usando:**  [Pesquisador de Objetos](#RGOffObjEx), [Propriedades do Resource Governor](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span><span class="sxs-lookup"><span data-stu-id="02381-105">**To disable Resource Governorn, using:**  [Object Explorer](#RGOffObjEx), [Resource Governor Properties](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02381-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="02381-106">Before You Begin</span></span>  
 <span data-ttu-id="02381-107">A desabilitação do Administrador de Recursos gera os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="02381-107">Disabling the Resource Governor has the following results:</span></span>  
  
-   <span data-ttu-id="02381-108">A função de classificação não é executada.</span><span class="sxs-lookup"><span data-stu-id="02381-108">The classifier function is not run.</span></span>  
  
-   <span data-ttu-id="02381-109">Todas as conexões novas são automaticamente classificadas no grupo de cargas de trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="02381-109">All new connections are automatically classified into the default workload group.</span></span>  
  
-   <span data-ttu-id="02381-110">As solicitações iniciadas pelo sistema são classificadas no grupo de cargas de trabalho interno.</span><span class="sxs-lookup"><span data-stu-id="02381-110">System-initiated requests are classified into the internal workload group.</span></span>  
  
-   <span data-ttu-id="02381-111">Todas as configurações existentes do grupo de carga de trabalho e do pool de recursos são redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="02381-111">All existing workload group and resource pool settings are reset to their default values.</span></span> <span data-ttu-id="02381-112">Nesse caso, nenhum evento é acionado quando os limites são atingidos.</span><span class="sxs-lookup"><span data-stu-id="02381-112">In this case, no events are fired when limits are reached.</span></span>  
  
-   <span data-ttu-id="02381-113">O monitoramento normal do sistema não é afetado.</span><span class="sxs-lookup"><span data-stu-id="02381-113">Normal system monitoring is not affected.</span></span>  
  
-   <span data-ttu-id="02381-114">As alterações de configuração podem ser feitas, mas as alterações não entram em vigor até que o Administrador de Recursos seja habilitado.</span><span class="sxs-lookup"><span data-stu-id="02381-114">Configuration changes can be made, but the changes do not take effect until the Resource Governor is enabled.</span></span>  
  
-   <span data-ttu-id="02381-115">Depois que o SQL Server for reiniciado, o Administrador de Recursos não carregará sua configuração, mas em vez disso terá apenas os grupos de cargas de trabalho e pools de recursos padrão e internos.</span><span class="sxs-lookup"><span data-stu-id="02381-115">Upon restarting SQL Server, the Resource Governor will not load its configuration, but instead will have only the default and internal workload groups and resource pools.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="02381-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="02381-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="02381-117">Você não pode usar a instrução `ALTER RESOURCE GOVERNOR` para desabilitar o Administrador de Recursos quando estiver em uma transação de usuário.</span><span class="sxs-lookup"><span data-stu-id="02381-117">You cannot use the `ALTER RESOURCE GOVERNOR` statement to disable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02381-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="02381-118">Permissions</span></span>  
 <span data-ttu-id="02381-119">Desabilitar o Administrador de Recursos exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="02381-119">Disabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="disable-resource-governor-using-object-explorer"></a><a name="RGOffObjEx"></a> <span data-ttu-id="02381-120">Desabilitar o Administrador de Recursos usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="02381-120">Disable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="02381-121">**Para desabilitar o Administrador de Recursos usando o Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="02381-121">**To disable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="02381-122">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="02381-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="02381-123">Clique com o botão direito do mouse em **Administrador de Recursos**e, então, clique em **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="02381-123">Right-click **Resource Governor**, and then click **Disable**.</span></span>  
  
##  <a name="disable-resource-governor-using-resource-governor-properties"></a><a name="RGOffProp"></a> <span data-ttu-id="02381-124">Desabilitar o Administrador de Recursos usando as Propriedades do Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="02381-124">Disable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="02381-125">**Para desabilitar o Administrador de Recursos usando a página de propriedades do Administrador de Recursos**</span><span class="sxs-lookup"><span data-stu-id="02381-125">**To disable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="02381-126">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="02381-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="02381-127">Clique com o botão direito do mouse em **Administrador de Recursos** e clique em **Propriedades**, para abrir a página **Propriedades do Administrador de Recursos** .</span><span class="sxs-lookup"><span data-stu-id="02381-127">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="02381-128">Clique na caixa de seleção **Habilitar Administrador de Recursos** , verifique se a caixa não está selecionada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="02381-128">Click the **Enable Resource Governor** check box, ensure that the box is not selected, and then click **OK**.</span></span>  
  
##  <a name="disable-resource-governor-using-transact-sql"></a><a name="RGOffTSQL"></a> <span data-ttu-id="02381-129">Desabilitar o Administrador de Recursos usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02381-129">Disable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="02381-130">**Para desabilitar o Administrador de Recursos usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="02381-130">**To disable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="02381-131">Execute a instrução **ALTER RESOURCE GOVERNOR DISABLE** .</span><span class="sxs-lookup"><span data-stu-id="02381-131">Run the **ALTER RESOURCE GOVERNOR DISABLE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="02381-132">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="02381-132">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="02381-133">O exemplo a seguir habilita o Administrador de Recursos.</span><span class="sxs-lookup"><span data-stu-id="02381-133">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR DISABLE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="02381-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02381-134">See Also</span></span>  
 <span data-ttu-id="02381-135">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="02381-135">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="02381-136">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="02381-136">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="02381-137">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="02381-137">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="02381-138">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="02381-138">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="02381-139">[Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="02381-139">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="02381-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="02381-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
