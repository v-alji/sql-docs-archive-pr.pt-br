---
title: Ferramentas e abordagens para processamento (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- process [Analysis Services]
- processing [Analysis Services]
ms.assetid: 82347a16-4145-4655-8adf-2a300f1fdf99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d2b28ecf29adc8240f76ec9888f9d4cb06dda887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574355"
---
# <a name="tools-and-approaches-for-processing-analysis-services"></a><span data-ttu-id="66bb4-102">Ferramentas e abordagens para processamento (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="66bb4-102">Tools and Approaches for Processing (Analysis Services)</span></span>
  <span data-ttu-id="66bb4-103">O processamento é uma operação em que o Analysis Services consulta uma fonte de dados relacional e popula objetos do Analysis Services usando esses dados.</span><span class="sxs-lookup"><span data-stu-id="66bb4-103">Processing is an operation in which Analysis Services queries a relational data source and populates Analysis Services objects using that data.</span></span>  
  
 <span data-ttu-id="66bb4-104">Como administrador do sistema do Analysis Services, você pode executar e monitorar o processamento de objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando estas abordagens:</span><span class="sxs-lookup"><span data-stu-id="66bb4-104">As an Analysis Services system administrator, you can execute and monitor the processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects using these approaches:</span></span>  
  
-   <span data-ttu-id="66bb4-105">Executar análise de impacto para entender as dependências de objeto e o escopo de operações</span><span class="sxs-lookup"><span data-stu-id="66bb4-105">Run Impact Analysis to understand object dependencies and scope of operations</span></span>  
  
-   <span data-ttu-id="66bb4-106">Processar objetos individuais no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66bb4-106">Process individual objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="66bb4-107">Processar objetos individuais ou múltiplos no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66bb4-107">Process individual or multiple objects in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="66bb4-108">Executar análise de impacto para analisar uma lista de objetos relacionados que terão o processamento cancelado como resultado da ação atual.</span><span class="sxs-lookup"><span data-stu-id="66bb4-108">Run Impact Analysis to review a list of related objects that will be unprocessed as result of the current action.</span></span>  
  
-   <span data-ttu-id="66bb4-109">Gerar e executar um script em uma janela de consulta XMLA do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para processar objetos individuais ou múltiplos</span><span class="sxs-lookup"><span data-stu-id="66bb4-109">Generate and run a script in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to process individual or multiple objects</span></span>  
  
-   <span data-ttu-id="66bb4-110">Usar cmdlets do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell</span><span class="sxs-lookup"><span data-stu-id="66bb4-110">Use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell cmdlets</span></span>  
  
-   <span data-ttu-id="66bb4-111">Usar fluxos de controle e tarefas em pacotes do [!INCLUDE[ssIS](../../includes/ssis-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66bb4-111">Use control flows and tasks in [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages</span></span>  
  
-   <span data-ttu-id="66bb4-112">Monitorar o processamento com o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="66bb4-112">Monitor processing with SQL Server Profiler</span></span>  
  
-   <span data-ttu-id="66bb4-113">Programar uma solução personalizada usando AMO.</span><span class="sxs-lookup"><span data-stu-id="66bb4-113">Program a custom solution using AMO.</span></span> <span data-ttu-id="66bb4-114">Para obter mais informações, consulte [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="66bb4-114">For more information, see [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span></span>  
  
 <span data-ttu-id="66bb4-115">O processamento é uma operação altamente configurável, controlada por um conjunto de opções de processamento que determinam se o processamento cheio ou incremental ocorre no nível do objeto.</span><span class="sxs-lookup"><span data-stu-id="66bb4-115">Processing is a highly configurable operation, controlled by a set of processing options that determine whether full or incremental processing occurs at the object level.</span></span> <span data-ttu-id="66bb4-116">Para obter mais informações sobre como processar opções e objetos, consulte [Opções e configurações de processamento &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) e [Processando objetos do Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="66bb4-116">For more information about processing options and objects, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) and [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66bb4-117">Este tópico descreve as ferramentas e as abordagens para processar modelos multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="66bb4-117">This topic describes the tools and approaches for processing multidimensional models.</span></span> <span data-ttu-id="66bb4-118">Para obter mais informações sobre o processamento de modelos de tabela, consulte [processar dados, tabela, ou partição](../tabular-models/process-database-table-or-partition-analysis-services.md) e [processos &#40;SSAS tabular&#41;](../process-data-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="66bb4-118">For more information about processing tabular models, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md) and [Process Data &#40;SSAS Tabular&#41;](../process-data-ssas-tabular.md).</span></span>  
  
### <a name="processing-objects-in-sql-server-management-studio"></a><span data-ttu-id="66bb4-119">Processando objetos no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66bb4-119">Processing objects in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="66bb4-120">Inicie o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e conecte-se ao Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="66bb4-120">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="66bb4-121">Clique com o botão direito do mouse no objeto do Analysis Services a ser processado e clique em **Processar**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-121">Right-click the Analysis Services object you want to process and then click **Process**.</span></span> <span data-ttu-id="66bb4-122">Você pode processar dados em qualquer um destes níveis:</span><span class="sxs-lookup"><span data-stu-id="66bb4-122">You can process data at any of these levels:</span></span>  
  
    -   <span data-ttu-id="66bb4-123">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="66bb4-123">Databases</span></span>  
  
    -   <span data-ttu-id="66bb4-124">Cubes</span><span class="sxs-lookup"><span data-stu-id="66bb4-124">Cubes</span></span>  
  
    -   <span data-ttu-id="66bb4-125">Grupos de medidas ou partições individuais no mesmo grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="66bb4-125">Measure Groups or individual partitions in the measure group</span></span>  
  
    -   <span data-ttu-id="66bb4-126">Dimensões</span><span class="sxs-lookup"><span data-stu-id="66bb4-126">Dimensions</span></span>  
  
    -   <span data-ttu-id="66bb4-127">Modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="66bb4-127">Mining Models</span></span>  
  
    -   <span data-ttu-id="66bb4-128">Estruturas de mineração</span><span class="sxs-lookup"><span data-stu-id="66bb4-128">Mining Structures</span></span>  
  
     <span data-ttu-id="66bb4-129">Objetos do Analysis Services são hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="66bb4-129">Analysis Services objects are hierarchical.</span></span> <span data-ttu-id="66bb4-130">Se você escolher o banco de dados, o processamento poderá ocorrer para todos os objetos contidos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="66bb4-130">If you choose database, processing can occur for all of the objects contained in the database.</span></span> <span data-ttu-id="66bb4-131">O real processamento depende da opção de processamento selecionada e do estado do objeto.</span><span class="sxs-lookup"><span data-stu-id="66bb4-131">Whether processing actually occurs will vary depending on the process option you select and the state of the object.</span></span> <span data-ttu-id="66bb4-132">Especificamente, se um objeto não for processado, o processamento de seu pai resultará no processamento desse objeto.</span><span class="sxs-lookup"><span data-stu-id="66bb4-132">Specifically, if an object is unprocessed, processing its parent will result in that object getting processed.</span></span> <span data-ttu-id="66bb4-133">Para obter mais informações sobre dependências de objeto, consulte [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="66bb4-133">For more information about object dependencies, see [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
3.  <span data-ttu-id="66bb4-134">Na caixa de diálogo **Processo** , em **Opções de Processo**, use o valor padrão fornecido ou selecione outra opção na lista.</span><span class="sxs-lookup"><span data-stu-id="66bb4-134">In the **Process** dialog box, in **Process Options**, use the default value provided or select a different option from the list.</span></span> <span data-ttu-id="66bb4-135">Para obter mais informações sobre cada opção, consulte [Opções e configurações de processamento &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="66bb4-135">For more information about each option, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="66bb4-136">Clique em **Análise de Impacto** para identificar e, opcionalmente, processar objetos dependentes que sejam afetados se os objetos listados na caixa de diálogo Processo forem processados.</span><span class="sxs-lookup"><span data-stu-id="66bb4-136">Click **Impact Analysis** to identify and optionally process dependent objects that are affected if the objects listed in the Process dialog box are processed.</span></span>  
  
5.  <span data-ttu-id="66bb4-137">Outra alternativa é clicar em **Alterar Configurações** para modificar a ordem de processamento, o comportamento do processamento relativo a tipos específicos de erros e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="66bb4-137">Optionally, click **Change Settings** to modify the processing order, processing behavior relative to specific types of errors, and other settings.</span></span>  
  
6.  <span data-ttu-id="66bb4-138">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-138">Click **OK**.</span></span>  
  
     <span data-ttu-id="66bb4-139">A caixa de diálogo Progresso do Processo fornece o status contínuo de cada comando.</span><span class="sxs-lookup"><span data-stu-id="66bb4-139">The Process Progress dialog box provides ongoing status for each command.</span></span> <span data-ttu-id="66bb4-140">Se uma mensagem de status estiver truncada, você poderá clicar em **Exibir Detalhes** para ler a mensagem inteira.</span><span class="sxs-lookup"><span data-stu-id="66bb4-140">If a status message is truncated, you can click **View Details** to read the entire message.</span></span>  
  
### <a name="processing-objects-in-sql-server-data-tools"></a><span data-ttu-id="66bb4-141">Processando objetos em ferramentas de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="66bb4-141">Processing Objects in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="66bb4-142">Inicie o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e abra um projeto que foi implantado.</span><span class="sxs-lookup"><span data-stu-id="66bb4-142">Start [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open a project that has been deployed.</span></span>  
  
2.  <span data-ttu-id="66bb4-143">Em Gerenciador de Soluções, no projeto implantado, expanda a pasta **Dimensões** .</span><span class="sxs-lookup"><span data-stu-id="66bb4-143">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
3.  <span data-ttu-id="66bb4-144">Clique com o botão direito do mouse em uma dimensão e clique em **Processar**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-144">Right-click a dimension, and then click **Process**.</span></span> <span data-ttu-id="66bb4-145">Você pode clicar com o botão direito em várias dimensões para processar vários objetos de uma vez.</span><span class="sxs-lookup"><span data-stu-id="66bb4-145">You can right-click multiple dimensions to process multiple objects at once.</span></span> <span data-ttu-id="66bb4-146">Para obter mais informações, consulte [Processamento em lotes &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="66bb4-146">For more information, see [Batch Processing &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="66bb4-147">Na caixa de diálogo **Processar Dimensão** , na coluna **Opções de Processo** na **Lista de objetos**, verifique se a opção dessa coluna é **Processar Completo**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-147">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="66bb4-148">Se essa opção não estiver selecionada, em **Opções de Processo**, clique na opção e selecione **Processar Completo** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="66bb4-148">If it is not, under **Process Options**, click the option, and select **Process Full** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="66bb4-149">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-149">Click **Run**.</span></span>  
  
6.  <span data-ttu-id="66bb4-150">Quando o processamento terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-150">When processing is finished, click **Close**.</span></span>  
  
##  <a name="run-impact-analysis-to-identify-object-dependencies-and-scope-of-operations"></a><a name="bkmk_impactanalysis"></a><span data-ttu-id="66bb4-151">Executar análise de impacto para identificar dependências de objeto e escopo de operações</span><span class="sxs-lookup"><span data-stu-id="66bb4-151">Run Impact Analysis to identify object dependencies and scope of operations</span></span>  
  
1.  <span data-ttu-id="66bb4-152">Antes de processar um objeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] ou no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], você pode analisar o efeito sobre objetos relacionados clicando em **Análise de Impacto** em uma das caixas de diálogo **Processar Objetos** .</span><span class="sxs-lookup"><span data-stu-id="66bb4-152">Before you process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object in either [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can analyze the effect on related objects by clicking **Impact Analysis** in one of the **Process Objects** dialog boxes.</span></span>  
  
2.  <span data-ttu-id="66bb4-153">Clique com o botão direito do mouse em uma dimensão, cubo, grupo de medidas ou partição para abrir uma caixa de diálogo **Processar Objetos** .</span><span class="sxs-lookup"><span data-stu-id="66bb4-153">Right-click a dimension, cube, measure group, or partition to open a **Process Objects** dialog box.</span></span>  
  
3.  <span data-ttu-id="66bb4-154">Clique em **Análise de Impacto**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-154">Click **Impact Analysis**.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="66bb4-155">examina o modelo e relata sobre o reprocessamento de requisitos para objetos que estão relacionados ao que você selecionou para processar.</span><span class="sxs-lookup"><span data-stu-id="66bb4-155">scans the model and reports on reprocessing requirements for objects that are related to the one you selected for processing.</span></span>  
  
### <a name="processing-objects-using-xmla"></a><span data-ttu-id="66bb4-156">Processando objetos usando o XMLA</span><span class="sxs-lookup"><span data-stu-id="66bb4-156">Processing objects using XMLA</span></span>  
  
1.  <span data-ttu-id="66bb4-157">Inicie o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e conecte-se ao Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="66bb4-157">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="66bb4-158">Clique com o botão direito do mouse no objeto a ser processado e, em seguida, clique em **Processo**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-158">Right-click the object to be processed and then click **Process**.</span></span>  
  
3.  <span data-ttu-id="66bb4-159">Na caixa de diálogo **Processo** , selecione a opção de processo que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="66bb4-159">In the **Process** dialog box, select the process option you want to use.</span></span> <span data-ttu-id="66bb4-160">Modifique outras configurações.</span><span class="sxs-lookup"><span data-stu-id="66bb4-160">Modify any other settings.</span></span> <span data-ttu-id="66bb4-161">Execute a Análise de Impacto para identificar as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="66bb4-161">Run Impact Analysis to identify any changes you might need to make.</span></span>  
  
4.  <span data-ttu-id="66bb4-162">Clique em **Script** na tela **Processar Objetos** .</span><span class="sxs-lookup"><span data-stu-id="66bb4-162">Click **Script** on the **Process Objects** screen.</span></span>  
  
     <span data-ttu-id="66bb4-163">Isto gera um script XMLA e abre uma janela Consulta XMLA do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66bb4-163">This generates an XMLA script and opens an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window.</span></span>  
  
5.  <span data-ttu-id="66bb4-164">Feche a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="66bb4-164">Close the dialog box.</span></span> <span data-ttu-id="66bb4-165">O script contém o comando de processamento e as opções especificadas na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="66bb4-165">The script contains the processing command and options that were specified in the dialog box.</span></span>  
  
6.  <span data-ttu-id="66bb4-166">Opcionalmente, você poderá continuar adicionando ao script se desejar processar outros objetos no mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="66bb4-166">Optionally, you can continue adding to the script if you want to process additional objects in the same batch.</span></span> <span data-ttu-id="66bb4-167">Para continuar, repita as etapas anteriores, adicionando o script gerado para que você tenha um único script para todas as operações de processamento.</span><span class="sxs-lookup"><span data-stu-id="66bb4-167">To continue, repeat the previous steps, appending the generated script so that you have a single script for all processing operations.</span></span> <span data-ttu-id="66bb4-168">Para exibir um exemplo, consulte [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="66bb4-168">To view an example, see [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span></span>  
  
7.  <span data-ttu-id="66bb4-169">Na barra de menus, clique em **Consulta**e, em seguida, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="66bb4-169">From the menu bar, click **Query**, and then click **Execute**.</span></span>  
  
### <a name="processing-objects-using-powershell"></a><span data-ttu-id="66bb4-170">Processando objetos usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="66bb4-170">Processing objects using PowerShell</span></span>  
  
1.  <span data-ttu-id="66bb4-171">A partir desta versão do SQL Server, você pode usar cmdlets do Analysis Services PowerShell para processar objetos.</span><span class="sxs-lookup"><span data-stu-id="66bb4-171">Starting in this release of SQL Server, you can use Analysis Services PowerShell cmdlets to process objects.</span></span> <span data-ttu-id="66bb4-172">Os seguintes cmdlets podem ser executados de forma interativa ou no script:</span><span class="sxs-lookup"><span data-stu-id="66bb4-172">The following cmdlets can be run interactively or in script:</span></span>  
  
    -   [<span data-ttu-id="66bb4-173">Cmdlet ProcessCube</span><span class="sxs-lookup"><span data-stu-id="66bb4-173">Invoke-ProcessCube cmdlet</span></span>](/powershell/module/sqlserver/invoke-processcube)  
  
    -   [<span data-ttu-id="66bb4-174">Cmdlet Invoke-ProcessDimension</span><span class="sxs-lookup"><span data-stu-id="66bb4-174">Invoke-ProcessDimension cmdlet</span></span>](/powershell/module/sqlserver/invoke-processdimension)  
  
    -   [<span data-ttu-id="66bb4-175">Cmdlet Invoke-ProcessPartition</span><span class="sxs-lookup"><span data-stu-id="66bb4-175">Invoke-ProcessPartition cmdlet</span></span>](/powershell/module/sqlserver/invoke-processpartition)  
  
    -   <span data-ttu-id="66bb4-176">[Cmdlet Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd), que pode ser usado para executar o script XMLA, MDX ou DMX que inclui comandos de processamento.</span><span class="sxs-lookup"><span data-stu-id="66bb4-176">[Invoke-ASCmd cmdlet](/powershell/module/sqlserver/invoke-ascmd), which can be used to execute XMLA, MDX, or DMX script that includes processing commands.</span></span>  
  
### <a name="monitoring-object-processing-using-sql-server-profiler"></a><span data-ttu-id="66bb4-177">Monitorando o processamento de objetos usando o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="66bb4-177">Monitoring object processing using SQL Server Profiler</span></span>  
  
1.  <span data-ttu-id="66bb4-178">Conectar a uma instância do Analysis Services no SQL Server Profiler.</span><span class="sxs-lookup"><span data-stu-id="66bb4-178">Connect to an Analysis Services instance in SQL Server Profiler.</span></span>  
  
2.  <span data-ttu-id="66bb4-179">Em Seleção de Eventos, clique em **Mostrar todos os eventos** para adicionar todos os eventos à lista.</span><span class="sxs-lookup"><span data-stu-id="66bb4-179">In Events Selection, click **Show all events** to add all events to the list.</span></span>  
  
3.  <span data-ttu-id="66bb4-180">Escolha os seguintes eventos:</span><span class="sxs-lookup"><span data-stu-id="66bb4-180">Choose the following events:</span></span>  
  
    -   <span data-ttu-id="66bb4-181">**Command Begin** e **Command End** para mostrar ao processar inícios e paradas</span><span class="sxs-lookup"><span data-stu-id="66bb4-181">**Command Begin** and **Command End** to show when processing starts and stops</span></span>  
  
    -   <span data-ttu-id="66bb4-182">**Error** para capturar erros</span><span class="sxs-lookup"><span data-stu-id="66bb4-182">**Error** to capture any errors</span></span>  
  
    -   <span data-ttu-id="66bb4-183">**Progress Report Begin**, **Progress Report Current**e **Progress Report End** para reportar sobre o status do processo e mostrar as consultas de SQL usadas para recuperar os dados</span><span class="sxs-lookup"><span data-stu-id="66bb4-183">**Progress Report Begin**, **Progress Report Current**, and **Progress Report End** to report on process status and show the SQL queries used to retrieve the data</span></span>  
  
    -   <span data-ttu-id="66bb4-184">**Execute MDX Script Begin** e **Execute MDX Script End** para mostrar os cálculos de cubo</span><span class="sxs-lookup"><span data-stu-id="66bb4-184">**Execute MDX Script Begin** and **Execute MDX Script End** to show the cube calculations</span></span>  
  
    -   <span data-ttu-id="66bb4-185">Opcionalmente, adicione eventos de bloqueio se você estiver diagnosticando problemas de desempenho relacionados ao processamento</span><span class="sxs-lookup"><span data-stu-id="66bb4-185">Optionally, add lock events if you are diagnosing performance problems related to processing</span></span>  
  
### <a name="process-analysis-services-objects-using-integration-services"></a><span data-ttu-id="66bb4-186">Processar objetos do Analysis Services usando Integration Services</span><span class="sxs-lookup"><span data-stu-id="66bb4-186">Process Analysis Services objects using Integration Services</span></span>  
  
1.  <span data-ttu-id="66bb4-187">No [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], crie um pacote que usa a Tarefa Processamento do Analysis Services para preencher os objetos automaticamente com novos dados quando você fizer atualizações regulares no banco de dados relacional de origem.</span><span class="sxs-lookup"><span data-stu-id="66bb4-187">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], create a package that uses the Analysis Services Processing Task to automatically populate objects with new data when you make regular updates to your source relational database.</span></span>  
  
2.  <span data-ttu-id="66bb4-188">Na **Caixa de Ferramentas do SSIS**, clique duas vezes em **Processamento do Analysis Services** para adicioná-lo ao pacote.</span><span class="sxs-lookup"><span data-stu-id="66bb4-188">In the **SSIS Toolbox**, double-click **Analysis Services Processing** to add it to the package.</span></span>  
  
3.  <span data-ttu-id="66bb4-189">Edite a tarefa para especificar uma conexão com o banco de dados, quais objetos processar e opção de processamento.</span><span class="sxs-lookup"><span data-stu-id="66bb4-189">Edit the task to specify a connection to the database, which objects to process, and the process option.</span></span> <span data-ttu-id="66bb4-190">Para obter mais informações sobre como implementar essa tarefa, consulte [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="66bb4-190">For more information about how to implement this task, see [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66bb4-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66bb4-191">See Also</span></span>  
 [<span data-ttu-id="66bb4-192">Processamento de objetos de modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="66bb4-192">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
