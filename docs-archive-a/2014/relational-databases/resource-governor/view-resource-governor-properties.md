---
title: Exibir propriedades do Administrador de Recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties.f1
helpviewer_keywords:
- Resource Governor, properties
ms.assetid: de3510df-f792-4a9d-80fa-f198fd36cdc8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cd7af8f4f8eb3cd0531bc907011846f73f94f6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572472"
---
# <a name="view-resource-governor-properties"></a><span data-ttu-id="cafd2-102">View Resource Governor Properties</span><span class="sxs-lookup"><span data-stu-id="cafd2-102">View Resource Governor Properties</span></span>
  <span data-ttu-id="cafd2-103">Você pode criar ou configurar entidades do Administrador de Recursos, como pools de recursos e grupos de cargas de trabalho, usando a página de Propriedades do Administrador de Recursos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cafd2-103">You can create or configure Resource Governor entities, such as resource pools and workload groups, by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="cafd2-104">**Antes de começar:**  [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="cafd2-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="cafd2-105">**Para exibir as propriedades do Administrador de Recursos usando:**  [Página de propriedades do Administrador de Recursos](#ViewRGProp)</span><span class="sxs-lookup"><span data-stu-id="cafd2-105">**To view Resource Governor properties, using:**  [Resource Governor Properties page](#ViewRGProp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cafd2-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cafd2-106">Before You Begin</span></span>  
 <span data-ttu-id="cafd2-107">Além de exibir as propriedades de entidades do Administrador de Recursos, você pode executar várias tarefas de configuração usando a página **Propriedades do Administrador de Recursos** .</span><span class="sxs-lookup"><span data-stu-id="cafd2-107">In addition to viewing the properties of Resource Governor entities, you can perform several configuration tasks using the **Resource Governor Properties** page.</span></span> <span data-ttu-id="cafd2-108">Para saber mais, consulte esses tópicos:</span><span class="sxs-lookup"><span data-stu-id="cafd2-108">For more information, see these topics:</span></span>  
  
-   [<span data-ttu-id="cafd2-109">Habilitar o Resource Governor</span><span class="sxs-lookup"><span data-stu-id="cafd2-109">Enable Resource Governor</span></span>](enable-resource-governor.md)  
  
-   [<span data-ttu-id="cafd2-110">Desabilitar o Resource Governor</span><span class="sxs-lookup"><span data-stu-id="cafd2-110">Disable Resource Governor</span></span>](disable-resource-governor.md)  
  
-   [<span data-ttu-id="cafd2-111">Criar um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="cafd2-111">Create a Resource Pool</span></span>](create-a-resource-pool.md)  
  
-   [<span data-ttu-id="cafd2-112">Criar um grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="cafd2-112">Create a Workload Group</span></span>](create-a-workload-group.md)  
  
-   [<span data-ttu-id="cafd2-113">Alterar configurações do pool de recursos</span><span class="sxs-lookup"><span data-stu-id="cafd2-113">Change Resource Pool Settings</span></span>](change-resource-pool-settings.md)  
  
-   [<span data-ttu-id="cafd2-114">Alterar as configurações do grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="cafd2-114">Change Workload Group Settings</span></span>](change-workload-group-settings.md)  
  
-   [<span data-ttu-id="cafd2-115">Mover um grupo de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="cafd2-115">Move a Workload Group</span></span>](move-a-workload-group.md)  
  
 <span data-ttu-id="cafd2-116">Quando você clicar em **OK** depois de adicionar, excluir ou mover um grupo de cargas de trabalho ou pool de recursos, a instrução ALTER RESOURCE GOVERNOR RECONFIGURE será executada.</span><span class="sxs-lookup"><span data-stu-id="cafd2-116">When you click **OK** after adding, deleting, or moving a workload group or resource pool, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
 <span data-ttu-id="cafd2-117">Se a operação de criação ou reconfiguração do pool de recursos ou grupo de cargas de trabalho falhar, um resumo de uma mensagem de erro será exibido abaixo do título da página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="cafd2-117">If the create or reconfigure operation for the resource pool or workload group fails, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="cafd2-118">Para visualizar uma mensagem de erro detalhada, clique na seta para baixo na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="cafd2-118">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
 <span data-ttu-id="cafd2-119">É possível determinar se há uma configuração pendente consultando a exibição de gerenciamento dinâmico de [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) para obter o status atual de is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="cafd2-119">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cafd2-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="cafd2-120">Permissions</span></span>  
 <span data-ttu-id="cafd2-121">Exibir propriedades do administrador de recursos exige a permissão VIEW SERVER STATER.</span><span class="sxs-lookup"><span data-stu-id="cafd2-121">Viewing resource governor properties requires VIEW SERVER STATER permission.</span></span> <span data-ttu-id="cafd2-122">As tarefas de configuração do administrador de recursos exigem a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="cafd2-122">The resource governor configuration tasks require CONTROL SERVER permission.</span></span>  
  
##  <a name="view-the-resource-governor-properties-page"></a><a name="ViewRGProp"></a><span data-ttu-id="cafd2-123">Exibir a página de propriedades de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="cafd2-123">View the Resource Governor Properties Page</span></span>  
 <span data-ttu-id="cafd2-124">**Para exibir as propriedades do administrador de recursos usando a página de Propriedades do Administrador de Recursos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="cafd2-124">**To view resource governor properties by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="cafd2-125">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o **Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="cafd2-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="cafd2-126">Clique com o botão direito do mouse em **Administrador de Recursos** e clique em **Propriedades**, para abrir a página **Propriedades do Administrador de Recursos** .</span><span class="sxs-lookup"><span data-stu-id="cafd2-126">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="cafd2-127">Para obter descrições dos campos na página, consulte [Propriedades do Administrador de Recursos](#RGProp).</span><span class="sxs-lookup"><span data-stu-id="cafd2-127">For descriptions of the fields in the page, see [Resource Governor Properties](#RGProp).</span></span>  
  
4.  <span data-ttu-id="cafd2-128">Para salvar as alterações, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cafd2-128">To save any changes, click **OK**.</span></span>  
  
##  <a name="resource-governor-properties"></a><a name="RGProp"></a><span data-ttu-id="cafd2-129">Propriedades de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="cafd2-129">Resource Governor Properties</span></span>  
 <span data-ttu-id="cafd2-130">**Nome da função de classificação**</span><span class="sxs-lookup"><span data-stu-id="cafd2-130">**Classifier function name**</span></span>  
 <span data-ttu-id="cafd2-131">Especifique a função de classificação selecionando-a na lista.</span><span class="sxs-lookup"><span data-stu-id="cafd2-131">Specify the classifier function by selecting from the list.</span></span>  
  
 <span data-ttu-id="cafd2-132">**Habilitar o Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="cafd2-132">**Enable Resource Governor**</span></span>  
 <span data-ttu-id="cafd2-133">Habilite ou desabilite o Administrador de Recursos selecionando ou desmarcando a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="cafd2-133">Enable or disable Resource Governor by selecting or clearing the check box.</span></span>  
  
 <span data-ttu-id="cafd2-134">**Pools de recursos**</span><span class="sxs-lookup"><span data-stu-id="cafd2-134">**Resource pools**</span></span>  
 <span data-ttu-id="cafd2-135">Crie ou altere a configuração do pool de recursos usando a grade fornecida.</span><span class="sxs-lookup"><span data-stu-id="cafd2-135">Create or change resource pool configuration by using the grid that is provided.</span></span> <span data-ttu-id="cafd2-136">Essa grade é populada com informações para os pools predefinidos internos e padrão.</span><span class="sxs-lookup"><span data-stu-id="cafd2-136">This grid is populated with information for the predefined internal and default pools.</span></span> <span data-ttu-id="cafd2-137">Selecione um pool com o qual trabalhar clicando na primeira coluna na linha do pool.</span><span class="sxs-lookup"><span data-stu-id="cafd2-137">Select a pool to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="cafd2-138">Para criar um novo pool de recursos, clique na linha antecedida pelo asterisco ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="cafd2-138">To create a new resource pool, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="cafd2-139">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cafd2-139">**Name**</span></span>  
 <span data-ttu-id="cafd2-140">Especifique o nome do pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="cafd2-140">Specify the name of the resource pool.</span></span>  
  
 <span data-ttu-id="cafd2-141">**% Mínima de CPU**</span><span class="sxs-lookup"><span data-stu-id="cafd2-141">**Minimum CPU %**</span></span>  
 <span data-ttu-id="cafd2-142">Especifique a média de largura de banda de CPU garantida para todas as solicitações no pool de recursos quando houver contenção de CPU.</span><span class="sxs-lookup"><span data-stu-id="cafd2-142">Specify the guaranteed average CPU bandwidth for all requests in the resource pool when there is CPU contention.</span></span> <span data-ttu-id="cafd2-143">O intervalo é de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="cafd2-143">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="cafd2-144">**% Máxima de CPU**</span><span class="sxs-lookup"><span data-stu-id="cafd2-144">**Maximum CPU %**</span></span>  
 <span data-ttu-id="cafd2-145">Especifique a média máxima de largura de banda de CPU que todas as solicitações desse pool de recursos receberão quando houver contenção de CPU.</span><span class="sxs-lookup"><span data-stu-id="cafd2-145">Specify the maximum average CPU bandwidth that all requests in this resource pool will receive when there is CPU contention.</span></span> <span data-ttu-id="cafd2-146">O intervalo é de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="cafd2-146">Range is 0 to 100.</span></span> <span data-ttu-id="cafd2-147">A configuração padrão é 100.</span><span class="sxs-lookup"><span data-stu-id="cafd2-147">The default setting is 100.</span></span>  
  
 <span data-ttu-id="cafd2-148">**% Mínima de Memória**</span><span class="sxs-lookup"><span data-stu-id="cafd2-148">**Minimum Memory %**</span></span>  
 <span data-ttu-id="cafd2-149">Especifique a quantidade mínima de memória reservada para esse pool de recursos que não pode ser compartilhada com outros pools de recursos.</span><span class="sxs-lookup"><span data-stu-id="cafd2-149">Specify the minimum amount of memory reserved for this resource pool that can not be shared with other resource pools.</span></span> <span data-ttu-id="cafd2-150">O intervalo é de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="cafd2-150">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="cafd2-151">**% Máxima de Memória**</span><span class="sxs-lookup"><span data-stu-id="cafd2-151">**Maximum Memory %**</span></span>  
 <span data-ttu-id="cafd2-152">Especifique a memória total de servidor que pode ser usada através de solicitações nesse pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="cafd2-152">Specify the total server memory that can be used by requests in this resource pool.</span></span> <span data-ttu-id="cafd2-153">O intervalo é de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="cafd2-153">Range is 0 to 100.</span></span> <span data-ttu-id="cafd2-154">A configuração padrão é 100.</span><span class="sxs-lookup"><span data-stu-id="cafd2-154">The default setting is 100.</span></span>  
  
 <span data-ttu-id="cafd2-155">Para obter mais informações, consulte [criar pool de recursos &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cafd2-155">For more information, see [CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span></span>  
  
 <span data-ttu-id="cafd2-156">**Grupos de cargas de trabalho para o pool de recursos**</span><span class="sxs-lookup"><span data-stu-id="cafd2-156">**Workload groups for resource pool**</span></span>  
 <span data-ttu-id="cafd2-157">Crie ou altere a configuração do grupo de carga de trabalho usando a grade fornecida.</span><span class="sxs-lookup"><span data-stu-id="cafd2-157">Create or change the workload group configuration by using the grid that is provided.</span></span> <span data-ttu-id="cafd2-158">Essa grade é populada com informações para os grupos predefinidos internos e padrão.</span><span class="sxs-lookup"><span data-stu-id="cafd2-158">This grid is populated with information for the predefined internal and default groups.</span></span> <span data-ttu-id="cafd2-159">Selecione um grupo com a qual trabalhar clicando na primeira coluna na linha para o pool.</span><span class="sxs-lookup"><span data-stu-id="cafd2-159">Select a group to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="cafd2-160">Para criar um novo grupo de carga de trabalho, clique na linha antecedida pelo asterisco ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="cafd2-160">To create a new workload group, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="cafd2-161">**Nome**</span><span class="sxs-lookup"><span data-stu-id="cafd2-161">**Name**</span></span>  
 <span data-ttu-id="cafd2-162">Especifique o nome do grupo de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cafd2-162">Specify the name of the workload group.</span></span>  
  
 <span data-ttu-id="cafd2-163">**Importância**</span><span class="sxs-lookup"><span data-stu-id="cafd2-163">**Importance**</span></span>  
 <span data-ttu-id="cafd2-164">Especifique a importância relativa de uma solicitação no grupo de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cafd2-164">Specify the relative importance of a request in the workload group.</span></span> <span data-ttu-id="cafd2-165">Configurações disponíveis são Baixa, Média, e Alta.</span><span class="sxs-lookup"><span data-stu-id="cafd2-165">Available settings are Low, Medium, and High.</span></span>  
  
 <span data-ttu-id="cafd2-166">**Máximo de Solicitações**</span><span class="sxs-lookup"><span data-stu-id="cafd2-166">**Maximum Requests**</span></span>  
 <span data-ttu-id="cafd2-167">Especifique o número máximo de solicitações simultâneas permitido para execução no grupo de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cafd2-167">Specify the maximum number of simultaneous requests that are allowed to execute in the workload group.</span></span> <span data-ttu-id="cafd2-168">O valor deve ser 0 ou um número inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="cafd2-168">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="cafd2-169">**Tempo de CPU (s)**</span><span class="sxs-lookup"><span data-stu-id="cafd2-169">**CPU Time (sec)**</span></span>  
 <span data-ttu-id="cafd2-170">Especifique o tempo máximo de CPU que uma solicitação pode usar.</span><span class="sxs-lookup"><span data-stu-id="cafd2-170">Specify the maximum amount of CPU time that a request can use.</span></span> <span data-ttu-id="cafd2-171">O valor deve ser 0 ou um número inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="cafd2-171">Must be 0 or a positive integer.</span></span> <span data-ttu-id="cafd2-172">Se 0, o tempo é ilimitado.</span><span class="sxs-lookup"><span data-stu-id="cafd2-172">If 0, the time is unlimited.</span></span>  
  
 <span data-ttu-id="cafd2-173">**% de Concessão de Memória**</span><span class="sxs-lookup"><span data-stu-id="cafd2-173">**Memory Grant %**</span></span>  
 <span data-ttu-id="cafd2-174">Especifique o máximo de memória que uma única solicitação pode usar do pool.</span><span class="sxs-lookup"><span data-stu-id="cafd2-174">Specify the maximum amount of memory that a single request can take from the pool.</span></span> <span data-ttu-id="cafd2-175">O intervalo é de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="cafd2-175">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="cafd2-176">**Tempo limite geral (segundo)**</span><span class="sxs-lookup"><span data-stu-id="cafd2-176">**Grant Time-out (sec)**</span></span>  
 <span data-ttu-id="cafd2-177">Especifique o tempo máximo que uma consulta pode esperar para que um recurso se torne disponível antes que a consulta falhe.</span><span class="sxs-lookup"><span data-stu-id="cafd2-177">Specify the maximum time that a query can wait for a resource to become available before the query fails.</span></span> <span data-ttu-id="cafd2-178">O valor deve ser 0 ou um número inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="cafd2-178">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="cafd2-179">**Grau de paralelismo**</span><span class="sxs-lookup"><span data-stu-id="cafd2-179">**Degree of Parallelism**</span></span>  
 <span data-ttu-id="cafd2-180">Especifique o grau máximo de paralelismo (DOP) para solicitações paralelas.</span><span class="sxs-lookup"><span data-stu-id="cafd2-180">Specify the maximum degree of parallelism (DOP) for parallel requests.</span></span> <span data-ttu-id="cafd2-181">O intervalo é de 0 a 64.</span><span class="sxs-lookup"><span data-stu-id="cafd2-181">Range is 0 to 64.</span></span>  
  
 <span data-ttu-id="cafd2-182">Para obter mais informações, consulte [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cafd2-182">For more information, see [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span></span>  
  
## <a name="view-resource-governor-properties-by-using-transact-sql"></a><span data-ttu-id="cafd2-183">Exibir as Propriedades do Administrador de Recursos usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cafd2-183">View Resource Governor Properties by Using Transact-SQL</span></span>  
 <span data-ttu-id="cafd2-184">**Exibir as propriedades do administrador de recursos usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="cafd2-184">**View resource governor properties by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="cafd2-185">Para exibir as definições de entidades do administrador de recursos, use o [Exibições do catálogo do administrador de recursos &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cafd2-185">To view the definitions of resource governor entities, use the [Resource Governor Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span></span>  
  
2.  <span data-ttu-id="cafd2-186">Para exibir a configuração atual de entidades do administrador de recursos, use o [Exibições de gerenciamento dinâmico relacionadas ao Administrador de Recursos &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cafd2-186">To view the current configuration of resource governor entities, use the [Resource Governor Related Dynamic Management Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafd2-187">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cafd2-187">See Also</span></span>  
 <span data-ttu-id="cafd2-188">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="cafd2-188">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="cafd2-189">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="cafd2-189">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="cafd2-190">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="cafd2-190">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="cafd2-191">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="cafd2-191">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 [<span data-ttu-id="cafd2-192">Função de classificação do Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="cafd2-192">Resource Governor Classifier Function</span></span>](resource-governor-classifier-function.md)  
  
  
