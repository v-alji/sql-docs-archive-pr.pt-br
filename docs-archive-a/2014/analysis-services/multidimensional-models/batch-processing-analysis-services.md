---
title: Processamento em lotes (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- batches [Analysis Services]
ms.assetid: ba4dcf72-0667-41d0-816b-ab8ff9a7d9cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: c777339f41f5f9029e4d03d47cc7f682e00032b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569705"
---
# <a name="batch-processing-analysis-services"></a><span data-ttu-id="aeb5b-102">Processamento em lotes (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="aeb5b-102">Batch Processing (Analysis Services)</span></span>
  <span data-ttu-id="aeb5b-103">No [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], você pode usar o comando Batch para enviar vários comandos de processamento para o servidor em uma única solicitação.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Batch command to send multiple processing commands to the server in a single request.</span></span> <span data-ttu-id="aeb5b-104">O processamento em lotes dá a você uma maneira de controlar quais objetos serão processados e em qual ordem.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-104">Batch processing gives you a way to control which objects are to be processed, and in what order.</span></span> <span data-ttu-id="aeb5b-105">Além disso, o processamento em lotes pode ser executado como uma série de trabalhos autônomos ou uma transação na qual a falha de um processo causa uma reversão do lote completo.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-105">Also, a batch can run as a series of stand-alone jobs, or as a transaction in which the failure of one process causes a rollback of the complete batch.</span></span>  
  
 <span data-ttu-id="aeb5b-106">O processamento em lotes maximiza a disponibilidade de dados consolidando e reduzindo a quantidade de tempo gasto para confirmar alterações.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-106">Batch processing maximizes data availability by consolidating and reducing the amount of time taken to commit changes.</span></span> <span data-ttu-id="aeb5b-107">Ao processar uma dimensão completamente, qualquer partição que usa aquela dimensão é marcada como não processada.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-107">When you fully process a dimension, any partition using that dimension is marked as unprocessed.</span></span> <span data-ttu-id="aeb5b-108">Como resultado, os cubos que contêm as partições não processadas ficam indisponíveis para navegar.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-108">As a result, cubes that contain the unprocessed partitions are unavailable for browsing.</span></span> <span data-ttu-id="aeb5b-109">Para resolver isso, use um trabalho de processamento em lotes e processe as dimensões junto com as partições afetadas.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-109">You can address this with a batch processing job by processing the dimensions together with the affected partitions.</span></span> <span data-ttu-id="aeb5b-110">A execução do trabalho de processamento em lotes como uma transação assegura que todos os objetos incluídos na transação permaneçam disponíveis para consulta até a conclusão do processamento.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-110">Running the batch processing job as a transaction makes sure that all objects included in the transaction remain available for queries until all processing is completed.</span></span> <span data-ttu-id="aeb5b-111">Como a transação confirma as alterações, são colocados bloqueios nos objetos afetados, tornando-os temporariamente indisponíveis, mas, em geral, a quantidade de tempo usada para confirmar as alterações é menor que se você tivesse processado os objetos individualmente.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-111">As the transaction commits the changes, locks are put on the affected objects, making the objects temporarily unavailable, but overall the amount of time used to commit the changes is less than if you processed objects individually.</span></span>  
  
 <span data-ttu-id="aeb5b-112">Os procedimentos neste tópico mostram as etapas para processar dimensões e partições completamente.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-112">The procedures in this topic show the steps for fully processing dimensions and partitions.</span></span> <span data-ttu-id="aeb5b-113">O processamento em lote também pode incluir outras opções de processamento, como o processamento incremental.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-113">Batch processing can also include other processing options, such as incremental processing.</span></span> <span data-ttu-id="aeb5b-114">Para esses procedimentos funcionarem corretamente, você deve usar um banco de dados existente do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém pelo menos duas dimensões e uma partição.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-114">For these procedures to work correctly, you should use an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains at least two dimensions and one partition.</span></span>  
  
 <span data-ttu-id="aeb5b-115">Este tópico inclui as seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="aeb5b-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="aeb5b-116">Processamento em lotes em Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="aeb5b-116">Batch Processing in SQL Server Data Tools</span></span>](#bkmk_ssdt)  
  
 [<span data-ttu-id="aeb5b-117">Processamento em lotes usando XMLA no Management Studio</span><span class="sxs-lookup"><span data-stu-id="aeb5b-117">Batch Processing using XMLA in Management Studio</span></span>](#bkmk_xmla)  
  
##  <a name="batch-processing-in-sql-server-data-tools"></a><a name="bkmk_ssdt"></a><span data-ttu-id="aeb5b-118">Processamento em lotes no SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="aeb5b-118">Batch Processing in SQL Server Data Tools</span></span>  
 <span data-ttu-id="aeb5b-119">Antes que os objetos possam ser processados no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], o projeto que contém os objetos deve ser implantado.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-119">Before objects can be processed in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], the project that contains the objects must be deployed.</span></span> <span data-ttu-id="aeb5b-120">Para obter mais informações, consulte [Implantar projetos do Analysis Services &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="aeb5b-120">For more information, see [Deploy Analysis Services Projects &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span></span>  
  
1.  <span data-ttu-id="aeb5b-121">Abra o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aeb5b-121">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="aeb5b-122">Abra um projeto que foi implantado.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-122">Open a project that has been deployed.</span></span>  
  
3.  <span data-ttu-id="aeb5b-123">Em Gerenciador de Soluções, no projeto implantado, expanda a pasta **Dimensões** .</span><span class="sxs-lookup"><span data-stu-id="aeb5b-123">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
4.  <span data-ttu-id="aeb5b-124">Com a tecla Ctrl pressionada, clique em cada dimensão listada na pasta **Dimensões** .</span><span class="sxs-lookup"><span data-stu-id="aeb5b-124">Holding the Ctrl key, click each dimension listed in the **Dimensions** folder.</span></span>  
  
5.  <span data-ttu-id="aeb5b-125">Clique com o botão direito do mouse nas dimensões selecionadas e escolha **Processar**.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-125">Right-click the selected dimensions, and then click **Process**.</span></span>  
  
6.  <span data-ttu-id="aeb5b-126">Com a tecla Ctrl pressionada, clique em cada dimensão listada na **Lista de objetos**.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-126">Holding the Ctrl key, click each dimension listed in the **Object list**.</span></span>  
  
7.  <span data-ttu-id="aeb5b-127">Clique com o botão direito do mouse nas dimensões selecionadas e escolha **Processar Completo**.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-127">Right-click the selected dimensions and select **Process Full**.</span></span>  
  
8.  <span data-ttu-id="aeb5b-128">Para personalizar o trabalho de processo em lote, clique em **Alterar Configurações**.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-128">To customize the batch process job, click **Change Settings.**</span></span>  
  
9. <span data-ttu-id="aeb5b-129">Em **Opções de processamento**, marque as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="aeb5b-129">Under **Processing options**, mark the following settings:</span></span>  
  
    -   <span data-ttu-id="aeb5b-130">**Ordem de processamento** é definido como **Sequencial**e **Modo de transação** é definido como **Uma Transação**.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-130">**Processing Order** is set to **Sequential**, and **Transaction mode** is set to **One Transaction**.</span></span>  
  
    -   <span data-ttu-id="aeb5b-131">**Opção da Tabela de Write-back** é definida como **Usar existente**.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-131">**Writeback Table Option** is set to **Use existing**.</span></span>  
  
    -   <span data-ttu-id="aeb5b-132">Em **Objetos Afetados**, marque a caixa de seleção **Objetos afetados pelo processo** .</span><span class="sxs-lookup"><span data-stu-id="aeb5b-132">Under **Affected Objects**, select the **Process affected objects** check box.</span></span>  
  
10. <span data-ttu-id="aeb5b-133">Clique na guia **erros de chave de dimensão** . Verifique se **usar configuração de erro padrão** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-133">Click the **Dimension key errors** tab. Verify that **Use default error configuration** is selected.</span></span>  
  
11. <span data-ttu-id="aeb5b-134">Clique em **OK** para fechar a tela **Alterar Configurações** .</span><span class="sxs-lookup"><span data-stu-id="aeb5b-134">Click **OK** to close the **Change Settings** screen.</span></span>  
  
12. <span data-ttu-id="aeb5b-135">Clique em **Executar** na tela **Processar Objetos** para iniciar o trabalho de processamento.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-135">Click **Run** in the **Process Objects** screen to start the processing job.</span></span>  
  
13. <span data-ttu-id="aeb5b-136">Quando a caixa **Status** mostrar **Processo com êxito**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-136">When the **Status** box shows **Process succeeded**, click **Close**.</span></span>  
  
14. <span data-ttu-id="aeb5b-137">Clique em **Fechar** na tela **Processar Objetos** .</span><span class="sxs-lookup"><span data-stu-id="aeb5b-137">Click **Close** on the **Process Objects** screen.</span></span>  
  
##  <a name="batch-processing-using-xmla-in-management-studio"></a><a name="bkmk_xmla"></a><span data-ttu-id="aeb5b-138">Processamento em lotes usando XMLA no Management Studio</span><span class="sxs-lookup"><span data-stu-id="aeb5b-138">Batch Processing using XMLA in Management Studio</span></span>  
 <span data-ttu-id="aeb5b-139">Você pode criar um script XMLA que executa processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-139">You can create an XMLA script that performs batch processing.</span></span> <span data-ttu-id="aeb5b-140">Inicie gerando um script XMLA no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para cada objeto e, em seguida, combine-os em uma única Consulta de XMLA que você executa interativamente ou dentro de uma tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="aeb5b-140">Start by generating an XMLA script in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] for each object, and then combine them into a single XMLA Query that you run interactively or inside a scheduled task.</span></span>  
  
 <span data-ttu-id="aeb5b-141">Para obter instruções passo a passo, consulte **Exemplo 2** em [Agendar tarefas administrativas do SSAS com o SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span><span class="sxs-lookup"><span data-stu-id="aeb5b-141">For step by step instructions, see **Example 2** in [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb5b-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aeb5b-142">See Also</span></span>  
 [<span data-ttu-id="aeb5b-143">Processamento de objetos de modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="aeb5b-143">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
