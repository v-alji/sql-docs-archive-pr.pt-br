---
title: Alterar as configurações do grupo de carga de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], alter
- Resource Governor, workload group alter
ms.assetid: 73b6109c-2ad0-4915-b11b-d40d5a0fdc25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 579aad71d32a629d75f1eecd76e7dacfe32d94f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568431"
---
# <a name="change-workload-group-settings"></a><span data-ttu-id="cd06d-102">Alterar as configurações de grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="cd06d-102">Change Workload Group Settings</span></span>
  <span data-ttu-id="cd06d-103">Você pode alterar as configurações do grupo de cargas de trabalho usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd06d-103">You can change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="cd06d-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="cd06d-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="cd06d-105">**Para alterar as configurações para um grupo de carga de trabalho usando:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="cd06d-105">**To change the settings for a workload group, using:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="cd06d-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cd06d-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="cd06d-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="cd06d-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="cd06d-108">Você pode alterar as configurações do grupo de cargas de trabalho padrão e de grupos de cargas de trabalho definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="cd06d-108">You can change the settings of the default workload group and user-defined workload groups.</span></span>  
  
 <span data-ttu-id="cd06d-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="cd06d-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="cd06d-110">A memória consumida pela criação de índice na tabela particionada desalinhada é proporcional ao número de partições envolvidas.</span><span class="sxs-lookup"><span data-stu-id="cd06d-110">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="cd06d-111">Se a memória total necessária exceder o limite por consulta (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposto pela configuração de grupo de cargas de trabalho, poderá ocorrer uma falha na criação do índice.</span><span class="sxs-lookup"><span data-stu-id="cd06d-111">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="cd06d-112">Como o grupo de cargas de trabalho padrão permite que uma consulta exceda o limite por consulta com o mínimo de memória requerida para iniciar, para compatibilidade com o SQL Server 2005, o usuário talvez possa executar a mesma criação de índice no grupo de cargas de trabalho padrão caso o pool de recursos padrão tenha memória total suficiente configurada para executar tal consulta.</span><span class="sxs-lookup"><span data-stu-id="cd06d-112">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="cd06d-113">A criação de índice pode usar mais workspace de memória do que aquela inicialmente concedida a fim de melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="cd06d-113">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="cd06d-114">Esse tratamento especial tem suporte do Administrador de Recursos. No entanto, a concessão inicial e qualquer concessão de memória adicional estão limitadas pelas configurações de pool de recursos e de grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cd06d-114">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cd06d-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="cd06d-115">Permissions</span></span>  
 <span data-ttu-id="cd06d-116">Alterar as configurações de um grupo de cargas de trabalho exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="cd06d-116">Changing workload group settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-workload-group-settings-using-sql-server-management-studio"></a><a name="ChgWGProp"></a> <span data-ttu-id="cd06d-117">Alterar as configurações do grupo de cargas de trabalho usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd06d-117">Change Workload Group Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="cd06d-118">**Para alterar as configurações do grupo de cargas de trabalho usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="cd06d-118">**To change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="cd06d-119">No Pesquisador de Objetos, expanda recursivamente o nó **Gerenciamento** para baixo e incluindo a pasta **Grupos de Cargas de Trabalho** que contém o grupo de carga de trabalho a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="cd06d-119">In Object Explorer, recursively expand the **Management** node down to and including the **Workload Groups** folder that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="cd06d-120">Clique com o botão direito do mouse no grupo de cargas de trabalho a ser modificado e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cd06d-120">Right-click the workload group to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="cd06d-121">Na página **Propriedades do Administrador de Recursos** selecione a linha para o grupo de cargas de trabalho na grade **Grupos de cargas de trabalho para o pool de recursos** caso não seja selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cd06d-121">In the **Resource Governor Properties** page, select the row for the workload group in the **Workload groups for resource pool** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="cd06d-122">Clique ou clique duas vezes nas células na linha a ser alterada e insira os novos valores.</span><span class="sxs-lookup"><span data-stu-id="cd06d-122">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="cd06d-123">Para salvar as alterações, clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="cd06d-123">To save the changes, click **OK**</span></span>  
  
##  <a name="change-workload-group-settings-using-transact-sql"></a><a name="ChgWGTSQL"></a> <span data-ttu-id="cd06d-124">Alterar configurações do grupo de cargas de trabalho usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd06d-124">Change Workload Group Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="cd06d-125">**Para alterar as configurações do grupo de cargas de trabalho usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="cd06d-125">**To change workload group settings by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="cd06d-126">Execute a instrução ALTER WORKLOAD GROUP que especifica os valores de propriedade a serem alterados.</span><span class="sxs-lookup"><span data-stu-id="cd06d-126">Run the ALTER WORKLOAD GROUP statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="cd06d-127">Execute a instrução ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="cd06d-127">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="cd06d-128">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cd06d-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="cd06d-129">O exemplo a seguir altera a configuração percentual de concessão de memória máxima para o grupo de cargas de trabalho chamado `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="cd06d-129">The following example changes the max memory grant percent setting for the workload group named `groupAdhoc`.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
WITH (REQUEST_MAX_MEMORY_GRANT_PERCENT = 30);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd06d-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cd06d-130">See Also</span></span>  
 <span data-ttu-id="cd06d-131">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="cd06d-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="cd06d-132">[Criar um grupo de carga de trabalho](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="cd06d-132">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="cd06d-133">[Criar um pool de recursos](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="cd06d-133">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="cd06d-134">[Alterar configurações do pool de recursos](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="cd06d-134">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="cd06d-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd06d-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="cd06d-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd06d-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="cd06d-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd06d-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
