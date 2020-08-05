---
title: Executar uma carga incremental de várias tabelas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],multiple tables
ms.assetid: 39252dd5-09c3-46f9-a17b-15208cfd336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf81d1d529e8102271c66839440ef712219600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570819"
---
# <a name="perform-an-incremental-load-of-multiple-tables"></a><span data-ttu-id="0cc15-102">Executar uma carga incremental de várias tabelas</span><span class="sxs-lookup"><span data-stu-id="0cc15-102">Perform an Incremental Load of Multiple Tables</span></span>
  <span data-ttu-id="0cc15-103">No tópico [Melhorando cargas incrementais com o Change Data Capture](change-data-capture-ssis.md), o diagrama ilustra um pacote básico que executa uma carga incremental em apenas uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0cc15-103">In the topic, [Improving Incremental Loads with Change Data Capture](change-data-capture-ssis.md), the diagram illustrates a basic package that performs an incremental load on just one table.</span></span> <span data-ttu-id="0cc15-104">No entanto, carregar uma tabela não é tão comum quanto ter que realizar uma carga incremental de diversas tabelas.</span><span class="sxs-lookup"><span data-stu-id="0cc15-104">However, loading one table is not as common as having to perform an incremental load of multiple tables.</span></span>  
  
 <span data-ttu-id="0cc15-105">Ao executar uma carga incremental de diversas tabelas, algumas etapas devem ser realizadas uma vez para todas as tabelas e outras etapas devem ser repetidas para cada tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="0cc15-105">When you perform an incremental load of multiple tables, some steps have to be performed once for all the tables, and other steps have to be repeated for each source table.</span></span> <span data-ttu-id="0cc15-106">Você tem mais de uma opção para implementar estas etapas no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0cc15-106">You have more than one option for implementing these steps in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="0cc15-107">Usar um pacote pai e pacotes filho.</span><span class="sxs-lookup"><span data-stu-id="0cc15-107">Use a parent package and child packages.</span></span>  
  
-   <span data-ttu-id="0cc15-108">Usar diversas tarefas de Fluxo de Dados em um único pacote.</span><span class="sxs-lookup"><span data-stu-id="0cc15-108">Use multiple Data Flow tasks in a single package.</span></span>  
  
## <a name="loading-multiple-tables-by-using-a-parent-package-and-multiple-child-packages"></a><span data-ttu-id="0cc15-109">Carregando diversas tabelas usando um pacote pai e diversos pacotes filho</span><span class="sxs-lookup"><span data-stu-id="0cc15-109">Loading Multiple Tables by Using a Parent Package and Multiple Child Packages</span></span>  
 <span data-ttu-id="0cc15-110">É possível usar um pacote pai para executar essas etapas que só precisam ser executadas uma vez.</span><span class="sxs-lookup"><span data-stu-id="0cc15-110">You can use a parent package to perform those steps that only have to be done once.</span></span> <span data-ttu-id="0cc15-111">Os pacotes filho executarão essas etapas que precisam ser executadas para cada tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="0cc15-111">The child packages will perform those steps that have to be done for each source table.</span></span>  
  
#### <a name="to-create-a-parent-package-that-performs-those-steps-that-only-have-to-be-done-once"></a><span data-ttu-id="0cc15-112">Para criar um pacote pai que executa essas etapas que só precisam ser executadas uma vez</span><span class="sxs-lookup"><span data-stu-id="0cc15-112">To create a parent package that performs those steps that only have to be done once</span></span>  
  
1.  <span data-ttu-id="0cc15-113">Crie um pacote pai.</span><span class="sxs-lookup"><span data-stu-id="0cc15-113">Create a parent package.</span></span>  
  
2.  <span data-ttu-id="0cc15-114">No fluxo de controle, use uma tarefa Executar SQL ou expressões do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para calcular os pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0cc15-114">In the control flow, use an Execute SQL task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="0cc15-115">Para obter um exemplo de como calcular os pontos de extremidade, consulte [Especificar um intervalo de dados de alteração](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-115">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="0cc15-116">Se necessário, use um contêiner Loop For para atrasar a execução até que os dados de alteração para o período selecionado estejam prontos.</span><span class="sxs-lookup"><span data-stu-id="0cc15-116">If needed, use a For Loop container to delay execution until change data for the selected period is ready.</span></span>  
  
     <span data-ttu-id="0cc15-117">Para obter um exemplo de um contêiner Loop For desse tipo, consulte [Determinar se os dados de alteração estão prontos](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-117">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="0cc15-118">Use diversas tarefas Executar Pacote para executar pacotes filho para cada tabela a ser carregada.</span><span class="sxs-lookup"><span data-stu-id="0cc15-118">Use multiple Execute Package tasks to execute child packages for each table to be loaded.</span></span> <span data-ttu-id="0cc15-119">Passe os pontos de extremidade calculados no pacote pai para cada pacote filho usando as Configurações de Variáveis do Pacote Pai.</span><span class="sxs-lookup"><span data-stu-id="0cc15-119">Pass the endpoints calculated in the parent package to each child package by using Parent Package Variable configurations.</span></span>  
  
     <span data-ttu-id="0cc15-120">Para obter mais informações, consulte [Tarefa Executar Pacote](../control-flow/execute-package-task.md) e [Usar os valores de variáveis e parâmetros em um pacote filho](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-120">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
#### <a name="to-create-child-packages-to-perform-those-steps-that-have-to-be-done-for-each-source-table"></a><span data-ttu-id="0cc15-121">Para criar pacotes filho para executar as etapas que precisam ser executadas para cada tabela de origem</span><span class="sxs-lookup"><span data-stu-id="0cc15-121">To create child packages to perform those steps that have to be done for each source table</span></span>  
  
1.  <span data-ttu-id="0cc15-122">Para cada tabela de origem, crie um pacote filho.</span><span class="sxs-lookup"><span data-stu-id="0cc15-122">For each source table, create a child package.</span></span>  
  
2.  <span data-ttu-id="0cc15-123">No fluxo de controle, use uma tarefa Script ou Executar SQL para montar a instrução SQL que será usada para consultar a existência de alterações.</span><span class="sxs-lookup"><span data-stu-id="0cc15-123">In the control flow, use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="0cc15-124">Para obter um exemplo de como montar a consulta, consulte [Preparar para consultar os dados de alteração](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-124">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
3.  <span data-ttu-id="0cc15-125">Use uma tarefa de Fluxo de Dados simples em cada pacote filho para carregar os dados de alteração e aplicá-los no destino.</span><span class="sxs-lookup"><span data-stu-id="0cc15-125">Use a single Data Flow task in each child package to load the change data and apply it to the destination.</span></span> <span data-ttu-id="0cc15-126">Configure o Fluxo de Dados conforme descrito nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0cc15-126">Configure the Data Flow as described in the following steps:</span></span>  
  
    1.  <span data-ttu-id="0cc15-127">No fluxo de dados, use um componente de origem para consultar as tabelas de alterações para as alterações que caem dentro dos pontos de extremidade selecionados.</span><span class="sxs-lookup"><span data-stu-id="0cc15-127">In the data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="0cc15-128">Para obter um exemplo de como consultar as tabelas de alteração, consulte [Recuperar e compreender os dados de alteração](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-128">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="0cc15-129">Use uma transformação de Divisão Condicional para direcionar as inserções, atualizações e exclusões para saídas diferentes para o processamento apropriado.</span><span class="sxs-lookup"><span data-stu-id="0cc15-129">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="0cc15-130">Para obter um exemplo de como configurar essa transformação para direcionar a saída, consulte [Processar inserções, atualizações e exclusões](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-130">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="0cc15-131">Use um componente de destino para aplicar as inserções ao destino.</span><span class="sxs-lookup"><span data-stu-id="0cc15-131">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="0cc15-132">Use as transformações de Comando OLE DB com as instruções UPDATE e DELETE com parâmetros para aplicar atualizações e exclusões ao destino.</span><span class="sxs-lookup"><span data-stu-id="0cc15-132">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="0cc15-133">Para obter um exemplo de como usar essa transformação para aplicar atualizações e exclusões, consulte [Aplicar as alterações ao destino](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-133">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
## <a name="loading-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="0cc15-134">Carregando diversas tabelas usando diversas tarefas de Fluxo de Dados em um único pacote</span><span class="sxs-lookup"><span data-stu-id="0cc15-134">Loading Multiple Tables by Using Multiple Data Flow Tasks in a Single Package</span></span>  
 <span data-ttu-id="0cc15-135">Como alternativa, é possível usar um único pacote que contém uma tarefa de Fluxo de Dados separado para cada tabela de origem que será carregada.</span><span class="sxs-lookup"><span data-stu-id="0cc15-135">Alternatively, you can use a single package that contains a separate Data Flow task for each source table to be loaded.</span></span>  
  
#### <a name="to-load-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="0cc15-136">Para carregar diversas tabelas usando diversas tarefas de Fluxo de Dados em um único pacote</span><span class="sxs-lookup"><span data-stu-id="0cc15-136">To load multiple tables by using multiple Data Flow tasks in a single package</span></span>  
  
1.  <span data-ttu-id="0cc15-137">Crie um único pacote.</span><span class="sxs-lookup"><span data-stu-id="0cc15-137">Create a single package.</span></span>  
  
2.  <span data-ttu-id="0cc15-138">No fluxo de controle, use uma Tarefa Executar SQL ou expressões do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para calcular os pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0cc15-138">In the control flow, use an Execute SQL Task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="0cc15-139">Para obter um exemplo de como calcular os pontos de extremidade, consulte [Especificar um intervalo de dados de alteração](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-139">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="0cc15-140">Se necessário, use um contêiner Loop For para atrasar a execução até que os dados de alteração para o intervalo selecionado estejam prontos.</span><span class="sxs-lookup"><span data-stu-id="0cc15-140">If needed, use a For Loop container to delay execution until the change data for the selected interval is ready.</span></span>  
  
     <span data-ttu-id="0cc15-141">Para obter um exemplo de um contêiner Loop For desse tipo, consulte [Determinar se os dados de alteração estão prontos](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-141">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="0cc15-142">Use uma tarefa Script ou Executar SQL para montar a instrução SQL que será usada para consultar a existência de alterações.</span><span class="sxs-lookup"><span data-stu-id="0cc15-142">Use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="0cc15-143">Para obter um exemplo de como montar a consulta, consulte [Preparar para consultar os dados de alteração](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-143">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
5.  <span data-ttu-id="0cc15-144">Use diversas tarefas de Fluxo de Dados para carregar os dados de alteração de cada tabela de origem e aplicá-los no destino.</span><span class="sxs-lookup"><span data-stu-id="0cc15-144">Use multiple Data Flow tasks to load the change data from each source table and apply it to the destination.</span></span> <span data-ttu-id="0cc15-145">Configure cada tarefa de Fluxo de Dados conforme descrito nas seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="0cc15-145">Configure each Data Flow task as described in the following steps.</span></span>  
  
    1.  <span data-ttu-id="0cc15-146">Em cada fluxo de dados, use um componente de origem para consultar as tabelas de alterações para as alterações que caem dentro dos pontos de extremidade selecionados.</span><span class="sxs-lookup"><span data-stu-id="0cc15-146">In each data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="0cc15-147">Para obter um exemplo de como consultar as tabelas de alteração, consulte [Recuperar e compreender os dados de alteração](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-147">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="0cc15-148">Use uma transformação de Divisão Condicional para direcionar as inserções, atualizações e exclusões para saídas diferentes para o processamento apropriado.</span><span class="sxs-lookup"><span data-stu-id="0cc15-148">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="0cc15-149">Para obter um exemplo de como configurar essa transformação para direcionar a saída, consulte [Processar inserções, atualizações e exclusões](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-149">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="0cc15-150">Use um componente de destino para aplicar as inserções ao destino.</span><span class="sxs-lookup"><span data-stu-id="0cc15-150">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="0cc15-151">Use as transformações de Comando OLE DB com as instruções UPDATE e DELETE com parâmetros para aplicar atualizações e exclusões ao destino.</span><span class="sxs-lookup"><span data-stu-id="0cc15-151">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="0cc15-152">Para obter um exemplo de como usar essa transformação para aplicar atualizações e exclusões, consulte [Aplicar as alterações ao destino](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0cc15-152">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
  
