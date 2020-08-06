---
title: Criar um pool de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource pools [SQL Server], create
- Resource Governor, resource pool create
ms.assetid: 44dd0567-a4c8-4c72-89ff-e76f6ddef344
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5abd2e60f4f9bb5290b47f95349782f8b26ad8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583475"
---
# <a name="create-a-resource-pool"></a><span data-ttu-id="faa90-102">Criar um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="faa90-102">Create a Resource Pool</span></span>
  <span data-ttu-id="faa90-103">É possível criar um pool de recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faa90-103">You can create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="faa90-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="faa90-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="faa90-105">**Para criar um pool de recursos usando:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="faa90-105">**To create a resource pool, using:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="faa90-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="faa90-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="faa90-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="faa90-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="faa90-108">O percentual máximo de CPU deve ser igual a ou maior que o percentual mínimo de CPU.</span><span class="sxs-lookup"><span data-stu-id="faa90-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="faa90-109">O percentual máximo de memória deve ser igual a ou maior que o percentual mínimo de memória.</span><span class="sxs-lookup"><span data-stu-id="faa90-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="faa90-110">A soma dos percentuais mínimos de CPU e dos percentuais mínimos de memória de todos os pools de recursos não deve exceder 100.</span><span class="sxs-lookup"><span data-stu-id="faa90-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="faa90-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="faa90-111">Permissions</span></span>  
 <span data-ttu-id="faa90-112">Criar um pool de recursos exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="faa90-112">Creating a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-resource-pool-using-sql-server-management-studio"></a><a name="CreRPProp"></a> <span data-ttu-id="faa90-113">Criar um pool de recursos usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="faa90-113">Create a Resource Pool Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="faa90-114">**Para criar um pool de recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="faa90-114">**To create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="faa90-115">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e inclua o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="faa90-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="faa90-116">Clique com o botão direito do mouse em **Resource Governor**e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="faa90-116">Right-click **Resource Governor**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="faa90-117">Na grade **Pools de recursos** , clique na primeira coluna na linha vazia.</span><span class="sxs-lookup"><span data-stu-id="faa90-117">In the **Resource pools** grid, click the first column in the empty row.</span></span> <span data-ttu-id="faa90-118">Essa coluna está rotulada com um asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="faa90-118">This column is labeled with an asterisk (\*).</span></span>  
  
4.  <span data-ttu-id="faa90-119">Clique duas vezes na célula vazia na coluna **Nome** .</span><span class="sxs-lookup"><span data-stu-id="faa90-119">Double-click the empty cell in the **Name** column.</span></span> <span data-ttu-id="faa90-120">Digite o nome que você quer usar para o pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="faa90-120">Type in the name that you want to use for the resource pool.</span></span>  
  
5.  <span data-ttu-id="faa90-121">Clique ou clique duas vezes em outras células na linha que você quer alterar e insira os novos valores.</span><span class="sxs-lookup"><span data-stu-id="faa90-121">Click or double-click any other cells in the row you want to change, and enter the new values.</span></span>  
  
6.  <span data-ttu-id="faa90-122">Para salvar as alterações, clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="faa90-122">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-resource-pool-using-transact-sql"></a><a name="CreRPTSQL"></a> <span data-ttu-id="faa90-123">Criar um pool de recursos usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="faa90-123">Create a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="faa90-124">**Para criar um pool de recursos usando o [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="faa90-124">**To create a resource pool by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="faa90-125">Execute a instrução `CREATE RESOURCE POOL` especificando os valores de propriedade a serem definidos.</span><span class="sxs-lookup"><span data-stu-id="faa90-125">Run the `CREATE RESOURCE POOL` statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="faa90-126">Execute a instrução **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="faa90-126">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="faa90-127">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="faa90-127">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="faa90-128">O exemplo a seguir cria um pool de recursos denominado `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="faa90-128">The following example creates a resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 20);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="faa90-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="faa90-129">See Also</span></span>  
 <span data-ttu-id="faa90-130">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-130">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="faa90-131">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-131">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="faa90-132">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-132">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="faa90-133">[Alterar configurações do pool de recursos](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-133">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="faa90-134">[Excluir um pool de recursos](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-134">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="faa90-135">[Configurar o administrador de recursos usando um modelo](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-135">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="faa90-136">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-136">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="faa90-137">[Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="faa90-137">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="faa90-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="faa90-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="faa90-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="faa90-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
