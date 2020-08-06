---
title: Habilitar Administrador de Recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, enabling
ms.assetid: 4d17af53-cf11-4ce4-aab4-deda94a49836
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b1b0f780457aa5a4d26cbb463c9f31a94185f0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680352"
---
# <a name="enable-resource-governor"></a><span data-ttu-id="4471c-102">Habilitar Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="4471c-102">Enable Resource Governor</span></span>
  <span data-ttu-id="4471c-103">O Administrador de Recursos é desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="4471c-103">The Resource Governor is turned off by default.</span></span> <span data-ttu-id="4471c-104">Você pode habilitar o Administrador de Recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="4471c-104">You can enable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="4471c-105">**Antes de começar:**  [Limitações e Restrições](#LimitationsRestrictions), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4471c-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="4471c-106">**Para habilitar o Administrador de Recursos usando:**  [Pesquisador de Objetos](#RGOnObjEx), [Propriedades do Resource Governor](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span><span class="sxs-lookup"><span data-stu-id="4471c-106">**To enable Resource Governorn, using:**  [Object Explorer](#RGOnObjEx), [Resource Governor Properties](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4471c-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4471c-107">Before You Begin</span></span>  
 <span data-ttu-id="4471c-108">A habilitação do administrador de recursos gera os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="4471c-108">Enabling the resource governor has the following results:</span></span>  
  
-   <span data-ttu-id="4471c-109">A função de classificação é executada para conexões novas, de forma que as cargas de trabalho possam ser atribuídas a grupos de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4471c-109">The classifier function is run for new connections so that their workloads can be assigned to workload groups.</span></span>  
  
-   <span data-ttu-id="4471c-110">Os limites de recursos especificados na configuração do Administrador de Recursos são cumpridos e impostos.</span><span class="sxs-lookup"><span data-stu-id="4471c-110">The resource limits that are specified in the Resource Governor configuration are honored and enforced.</span></span>  
  
-   <span data-ttu-id="4471c-111">As solicitações existentes antes da habilitação do Administrador de Recursos são afetadas por todas as alterações feitas na configuração quando o Administrador de Recursos foi desabilitado.</span><span class="sxs-lookup"><span data-stu-id="4471c-111">Requests that existed before enabling Resource Governor are affected by any configuration changes that were made when the Resource Governor was disabled.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="4471c-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4471c-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4471c-113">Você não pode usar a instrução `ALTER RESOURCE GOVERNOR` para habilitar o Administrador de Recursos quando estiver em uma transação de usuário.</span><span class="sxs-lookup"><span data-stu-id="4471c-113">You cannot use the `ALTER RESOURCE GOVERNOR` statement to enable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4471c-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="4471c-114">Permissions</span></span>  
 <span data-ttu-id="4471c-115">Habilitar o Administrador de Recursos exige permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4471c-115">Enabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="enable-resource-governor-using-object-explorer"></a><a name="RGOnObjEx"></a> <span data-ttu-id="4471c-116">Habilitar o Administrador de Recursos usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="4471c-116">Enable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="4471c-117">**Para habilitar o Administrador de Recursos usando o Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="4471c-117">**To enable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="4471c-118">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="4471c-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="4471c-119">Clique com o botão direito do mouse em **Resource Governor**e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="4471c-119">Right-click **Resource Governor**, and then click **Enable**.</span></span>  
  
##  <a name="enable-resource-governor-using-resource-governor-properties"></a><a name="RGOnProp"></a> <span data-ttu-id="4471c-120">Habilitar o Administrador de Recursos usando as Propriedades do Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="4471c-120">Enable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="4471c-121">**Para habilitar o Administrador de Recursos usando a página de propriedades do Administrador de Recursos**</span><span class="sxs-lookup"><span data-stu-id="4471c-121">**To enable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="4471c-122">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="4471c-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="4471c-123">Clique com o botão direito do mouse em **Administrador de Recursos** e clique em **Propriedades**, para abrir a página **Propriedades do Administrador de Recursos** .</span><span class="sxs-lookup"><span data-stu-id="4471c-123">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="4471c-124">Clique na caixa de seleção **Habilitar Administrador de Recursos** e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4471c-124">Click the **Enable Resource Governor** check box, and then click **OK**.</span></span>  
  
##  <a name="enable-resource-governor-using-transact-sql"></a><a name="RGOnTSQL"></a> <span data-ttu-id="4471c-125">Habilitar o Administrador de Recursos usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4471c-125">Enable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="4471c-126">**Para habilitar o Administrador de Recursos usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4471c-126">**To enable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="4471c-127">Execute a instrução **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="4471c-127">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="4471c-128">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4471c-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4471c-129">O exemplo a seguir habilita o Administrador de Recursos.</span><span class="sxs-lookup"><span data-stu-id="4471c-129">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4471c-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4471c-130">See Also</span></span>  
 <span data-ttu-id="4471c-131">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4471c-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="4471c-132">[Desabilitar Administrador de Recursos](disable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4471c-132">[Disable Resource Governor](disable-resource-governor.md) </span></span>  
 <span data-ttu-id="4471c-133">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="4471c-133">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="4471c-134">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="4471c-134">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="4471c-135">[Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="4471c-135">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="4471c-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4471c-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
