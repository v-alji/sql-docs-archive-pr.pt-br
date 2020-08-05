---
title: Criar um grupo de carga de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group create
- workload groups [SQL Server], create
ms.assetid: 072868ec-ceff-4db6-941b-281af731a067
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 144bcef57b3d6e191b03b1539e9e7382a9085c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572476"
---
# <a name="create-a-workload-group"></a><span data-ttu-id="1dfa8-102">Criar um grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="1dfa8-102">Create a Workload Group</span></span>
  <span data-ttu-id="1dfa8-103">Você pode criar um grupo de cargas de trabalho usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dfa8-103">You can create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="1dfa8-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="1dfa8-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="1dfa8-105">**Para criar um grupo de carga de trabalho usando:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="1dfa8-105">**To create a workload group, using:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1dfa8-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1dfa8-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="1dfa8-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="1dfa8-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1dfa8-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="1dfa8-109">A memória consumida pela criação de índice na tabela particionada desalinhada é proporcional ao número de partições envolvidas.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-109">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="1dfa8-110">Se a memória total necessária exceder o limite por consulta (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposto pela configuração de grupo de cargas de trabalho, poderá ocorrer uma falha na criação do índice.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-110">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="1dfa8-111">Como o grupo de cargas de trabalho padrão permite que uma consulta exceda o limite por consulta com o mínimo de memória requerida para iniciar, para compatibilidade com o SQL Server 2005, o usuário talvez possa executar a mesma criação de índice no grupo de cargas de trabalho padrão caso o pool de recursos padrão tenha memória total suficiente configurada para executar tal consulta.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-111">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="1dfa8-112">A criação de índice pode usar mais workspace de memória do que aquela inicialmente concedida a fim de melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-112">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="1dfa8-113">Esse tratamento especial tem suporte do Administrador de Recursos. No entanto, a concessão inicial e qualquer concessão de memória adicional estão limitadas pelas configurações de pool de recursos e de grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-113">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1dfa8-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="1dfa8-114">Permissions</span></span>  
 <span data-ttu-id="1dfa8-115">Criar um grupo de cargas de trabalho exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-115">Creating a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-workload-group-using-sql-server-management-studio"></a><a name="CreWGProp"></a> <span data-ttu-id="1dfa8-116">Criar um grupo de cargas de trabalho usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1dfa8-116">Create a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1dfa8-117">**Para criar um grupo de cargas de trabalho usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-117">**To create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="1dfa8-118">No Pesquisador de Objetos, expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o pool de recursos que contém o grupo de cargas de trabalho a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-118">In Object Explorer, recursively expand the **Management** node down to and including the resource pool that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="1dfa8-119">Clique com o botão direito do mouse na pasta **Grupos de Cargas de Trabalho** e clique em **Novo Grupo de Cargas de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-119">Right-click the **Workload Groups** folder, and then click **New Workload Group**.</span></span>  
  
3.  <span data-ttu-id="1dfa8-120">Na grade **Pools de recursos** , verifique se o pool de recursos onde você deseja adicionar o grupo de cargas de trabalho está realçado.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-120">In the **Resource pools** grid, ensure the resource pool where you want to add the workload group is highlighted.</span></span>  
  
4.  <span data-ttu-id="1dfa8-121">A grade **Grupos de cargas de trabalho para pool de recursos** terão uma nova linha com um nome em branco e valores padrão nas outras colunas.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-121">The **Workload groups for resource pool** grid will have a new line with a blank name and default values in the other columns.</span></span>  
  
5.  <span data-ttu-id="1dfa8-122">Clique na célula **Nome** e insira o nome do grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-122">Click the **Name** cell and enter a name for the workload group.</span></span>  
  
6.  <span data-ttu-id="1dfa8-123">Clique ou clique duas vezes em outras células na linha que você quer alterar das configurações padrão e insira os novos valores.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-123">Click or double-click any other cells in the row you want to change from their default settings, and enter the new values.</span></span>  
  
7.  <span data-ttu-id="1dfa8-124">Para salvar as alterações, clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-124">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-workload-group-using-transact-sql"></a><a name="CreWGTSQL"></a> <span data-ttu-id="1dfa8-125">Criar grupo de cargas de trabalho usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1dfa8-125">Create a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="1dfa8-126">**Para criar um grupo de cargas de trabalho usando o [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-126">**To create a workload group by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="1dfa8-127">Execute a instrução CREATE WORKLOAD GROUP que especifica os valores de propriedade a serem definidos.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-127">Run the CREATE WORKLOAD GROUP statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="1dfa8-128">Execute a instrução ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-128">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="1dfa8-129">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1dfa8-129">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="1dfa8-130">O exemplo a seguir cria um grupo de cargas de trabalho chamado `groupAdhoc` no pool de recursos chamado `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-130">The following example creates a workload group named `groupAdhoc` in the resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE WORKLOAD GROUP groupAdhoc  
USING poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1dfa8-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1dfa8-131">See Also</span></span>  
 <span data-ttu-id="1dfa8-132">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="1dfa8-132">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="1dfa8-133">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="1dfa8-133">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="1dfa8-134">[Criar um pool de recursos](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="1dfa8-134">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="1dfa8-135">[Alterar as configurações de grupo de carga de trabalho](change-workload-group-settings.md) </span><span class="sxs-lookup"><span data-stu-id="1dfa8-135">[Change Workload Group Settings](change-workload-group-settings.md) </span></span>  
 <span data-ttu-id="1dfa8-136">[Criar e testar uma função de classificação definida pelo usuário](create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="1dfa8-136">[Create and Test a Classifier User-Defined Function](create-and-test-a-classifier-user-defined-function.md) </span></span>  
 <span data-ttu-id="1dfa8-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1dfa8-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="1dfa8-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1dfa8-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
