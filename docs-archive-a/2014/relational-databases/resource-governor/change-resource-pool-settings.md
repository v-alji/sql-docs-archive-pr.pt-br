---
title: Alterar as configurações do pool de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool alter
- resource pools [SQL Server], alter
ms.assetid: 49438285-a011-4dac-bd4f-f35cd90fda61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2183cceaaf8a3e183d96c154075f9a922942c2c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679846"
---
# <a name="change-resource-pool-settings"></a><span data-ttu-id="8fadd-102">Alterar configurações do pool de recursos</span><span class="sxs-lookup"><span data-stu-id="8fadd-102">Change Resource Pool Settings</span></span>
  <span data-ttu-id="8fadd-103">É possível alterar as configurações de um pool de recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fadd-103">You can change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="8fadd-104">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="8fadd-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="8fadd-105">**Para alterar as configurações para um pool de recursos usando:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="8fadd-105">**To change the settings for a resource pool, using:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8fadd-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8fadd-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="8fadd-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8fadd-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8fadd-108">O percentual máximo de CPU deve ser igual a ou maior que o percentual mínimo de CPU.</span><span class="sxs-lookup"><span data-stu-id="8fadd-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="8fadd-109">O percentual máximo de memória deve ser igual a ou maior que o percentual mínimo de memória.</span><span class="sxs-lookup"><span data-stu-id="8fadd-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="8fadd-110">A soma dos percentuais mínimos de CPU e dos percentuais mínimos de memória de todos os pools de recursos não deve exceder 100.</span><span class="sxs-lookup"><span data-stu-id="8fadd-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8fadd-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="8fadd-111">Permissions</span></span>  
 <span data-ttu-id="8fadd-112">Alterar as configurações do pool de recursos exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="8fadd-112">Changing resource pool settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-resource-pool-settings-using-sql-server-management-studio"></a><a name="ChgRPProp"></a> <span data-ttu-id="8fadd-113">Alterar as configurações do pool de recursos usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8fadd-113">Change Resource Pool Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8fadd-114">**Para alterar as configurações de um pool de recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="8fadd-114">**To change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="8fadd-115">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e inclua **Pools de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="8fadd-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="8fadd-116">Clique com o botão direito do mouse no pool de recursos a ser modificado e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8fadd-116">Right-click the resource pool to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8fadd-117">Na página **Propriedades do Administrador de Recursos** selecione a linha para o pool de recursos na grade **Pools de Recursos** caso ela não seja selecionada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8fadd-117">In the **Resource Governor Properties** page, select the row for the resource pool in the **Resource pools** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="8fadd-118">Clique ou clique duas vezes nas células na linha a ser alterada e insira os novos valores.</span><span class="sxs-lookup"><span data-stu-id="8fadd-118">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="8fadd-119">Para salvar as alterações, clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="8fadd-119">To save the changes, click **OK**</span></span>  
  
##  <a name="change-resource-pool-settings-using-transact-sql"></a><a name="ChgRPTSQL"></a> <span data-ttu-id="8fadd-120">Alterar o pool de recursos usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8fadd-120">Change Resource Pool Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="8fadd-121">**Para alterar as configurações de um pool de recursos usando o [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="8fadd-121">**To change resource pool settings by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="8fadd-122">Execute a instrução `ALTER RESOURCE POOL` especificando os valores de propriedade a serem alterados.</span><span class="sxs-lookup"><span data-stu-id="8fadd-122">Run the `ALTER RESOURCE POOL` statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="8fadd-123">Execute a instrução **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="8fadd-123">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="8fadd-124">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8fadd-124">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="8fadd-125">O exemplo a seguir altera a configuração do percentual máximo de CPU para o pool de recursos chamada `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="8fadd-125">The following example changes the max CPU percentage setting for the resource pool named `poolAdhoc`.</span></span>  
  
```  
ALTER RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 25);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fadd-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8fadd-126">See Also</span></span>  
 <span data-ttu-id="8fadd-127">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="8fadd-127">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="8fadd-128">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="8fadd-128">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="8fadd-129">[Criar um pool de recursos](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="8fadd-129">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="8fadd-130">[Excluir um pool de recursos](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="8fadd-130">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="8fadd-131">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="8fadd-131">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="8fadd-132">[Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="8fadd-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="8fadd-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8fadd-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="8fadd-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8fadd-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
