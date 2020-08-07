---
title: Processar dados manualmente (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.datarefreshprogressdb.f1
ms.assetid: 0918c04c-c1e6-45b4-acfa-96fa578e684b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51bdb1b9535685db4fc35dbdd791e6b4d9bed1b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581573"
---
# <a name="manually-process-data-ssas-tabular"></a><span data-ttu-id="37b92-102">Processando os dados manualmente (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="37b92-102">Manually Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="37b92-103">Este tópico descreve como processar manualmente dados de workspace no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37b92-103">This topic describes how to manually process workspace data in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="37b92-104">Ao criar um modelo de tabela que usa dados externos, é possível atualizar os dados manualmente usando o comando Processar.</span><span class="sxs-lookup"><span data-stu-id="37b92-104">When you author a tabular model that uses external data, you can manually refresh the data by using the Process command.</span></span> <span data-ttu-id="37b92-105">Você pode processar uma única tabela, todas as tabelas no modelo ou uma ou mais partições.</span><span class="sxs-lookup"><span data-stu-id="37b92-105">You can process a single table, all tables in the model, or one or more partitions.</span></span> <span data-ttu-id="37b92-106">Sempre que os dados são processados, também pode ser necessário recalculá-los.</span><span class="sxs-lookup"><span data-stu-id="37b92-106">Whenever you process data, you may also need to recalculate data.</span></span>  <span data-ttu-id="37b92-107">Processar os dados significa obter os dados mais recentes de fontes externas.</span><span class="sxs-lookup"><span data-stu-id="37b92-107">Processing data means getting the latest data from external sources.</span></span> <span data-ttu-id="37b92-108">Recalcular significa atualizar o resultado de qualquer fórmula que usa os dados.</span><span class="sxs-lookup"><span data-stu-id="37b92-108">Recalculating means updating the result of any formula that uses the data.</span></span>  
  
 <span data-ttu-id="37b92-109">Seções neste tópico:</span><span class="sxs-lookup"><span data-stu-id="37b92-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="37b92-110">Processando os dados manualmente</span><span class="sxs-lookup"><span data-stu-id="37b92-110">Manually Process Data</span></span>](#bkmk_mahually_process)  
  
-   [<span data-ttu-id="37b92-111">Progresso do Processo de Dados</span><span class="sxs-lookup"><span data-stu-id="37b92-111">Data Process Progress</span></span>](#bkmk_data_process_progress)  
  
##  <a name="manually-process-data"></a><a name="bkmk_mahually_process"></a><span data-ttu-id="37b92-112">Processar dados manualmente</span><span class="sxs-lookup"><span data-stu-id="37b92-112">Manually Process Data</span></span>  
  
#### <a name="to-process-data-for-a-single-table-or-all-tables-in-a-model"></a><span data-ttu-id="37b92-113">Para processar dados de uma única tabela ou de todas as tabelas em um modelo</span><span class="sxs-lookup"><span data-stu-id="37b92-113">To process data for a single table or all tables in a model</span></span>  
  
1.  <span data-ttu-id="37b92-114">No designer de modelos, clique na tabela que você quer processar.</span><span class="sxs-lookup"><span data-stu-id="37b92-114">In the model designer, click the table you want to process.</span></span>  
  
2.  <span data-ttu-id="37b92-115">Clique no menu **Modelo** , clique em **Processar**e clique em **Processar** ou **Processar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="37b92-115">Click on the **Model** menu, then click **Process**, and then click **Process** or **Process All**.</span></span>  
  
#### <a name="to-process-data-for-all-tables-using-the-same-connection"></a><span data-ttu-id="37b92-116">Para processar dados para todas as tabelas usando a mesma conexão</span><span class="sxs-lookup"><span data-stu-id="37b92-116">To process data for all tables using the same connection</span></span>  
  
1.  <span data-ttu-id="37b92-117">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Modelo** e em **Conexões Existentes**.</span><span class="sxs-lookup"><span data-stu-id="37b92-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="37b92-118">Na caixa de diálogo **Conexões Existentes** , selecione uma conexão, e clique em **Processar**.</span><span class="sxs-lookup"><span data-stu-id="37b92-118">In the **Existing Connections** dialog box, select a connection, and then click **Process**.</span></span>  
  
#### <a name="to-process-data-for-one-or-more-partitions"></a><span data-ttu-id="37b92-119">Para processar dados para uma ou mais partições</span><span class="sxs-lookup"><span data-stu-id="37b92-119">To process data for one or more partitions</span></span>  
  
1.  <span data-ttu-id="37b92-120">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Modelo** , aponte para **Processar**e em **Processar Partições**.</span><span class="sxs-lookup"><span data-stu-id="37b92-120">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Process**, and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="37b92-121">Na caixa de diálogo **Processar Partições** , em **Modo**, selecione um dos modos de processo a seguir:</span><span class="sxs-lookup"><span data-stu-id="37b92-121">In the **Process Partitions** dialog box, in **Mode**, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="37b92-122">Mode</span><span class="sxs-lookup"><span data-stu-id="37b92-122">Mode</span></span>|<span data-ttu-id="37b92-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="37b92-123">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="37b92-124">**Processar Padrão**</span><span class="sxs-lookup"><span data-stu-id="37b92-124">**Process Default**</span></span>|<span data-ttu-id="37b92-125">Detecta o estado de processamento de um objeto de partição e realiza o processamento necessário para passar os objetos de partição não processados ou parcialmente processados para um estado completamente processado.</span><span class="sxs-lookup"><span data-stu-id="37b92-125">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="37b92-126">Os dados para tabelas vazias e partições são carregados; hierarquias, colunas calculadas e relações são criadas ou recriadas.</span><span class="sxs-lookup"><span data-stu-id="37b92-126">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="37b92-127">**Processar Completo**</span><span class="sxs-lookup"><span data-stu-id="37b92-127">**Process Full**</span></span>|<span data-ttu-id="37b92-128">Processa um objeto de partição e todos os objetos que ele contém.</span><span class="sxs-lookup"><span data-stu-id="37b92-128">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="37b92-129">Quando o comando Processar Completo for executado para um objeto que já foi processado, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] removerá todos os dados do objeto e processará o objeto.</span><span class="sxs-lookup"><span data-stu-id="37b92-129">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="37b92-130">Esse tipo de processamento é necessário quando uma alteração estrutural é feita em um objeto.</span><span class="sxs-lookup"><span data-stu-id="37b92-130">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="37b92-131">**Processar dados**</span><span class="sxs-lookup"><span data-stu-id="37b92-131">**Process Data**</span></span>|<span data-ttu-id="37b92-132">Carregue os dados em uma partição ou uma tabela sem recriar hierarquias ou relações ou recalcular colunas calculadas e medidas.</span><span class="sxs-lookup"><span data-stu-id="37b92-132">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="37b92-133">**Processar Limpeza**</span><span class="sxs-lookup"><span data-stu-id="37b92-133">**Process Clear**</span></span>|<span data-ttu-id="37b92-134">Remove todos os dados de uma partição.</span><span class="sxs-lookup"><span data-stu-id="37b92-134">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="37b92-135">**Processar adição**</span><span class="sxs-lookup"><span data-stu-id="37b92-135">**Process Add**</span></span>|<span data-ttu-id="37b92-136">Atualize a partição incrementalmente com novos dados.</span><span class="sxs-lookup"><span data-stu-id="37b92-136">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="37b92-137">Na lista de partições, selecione as partições que você deseja processar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="37b92-137">In the partitions list, select the partitions you want to process, and then click **OK**.</span></span>  
  
##  <a name="data-process-progress"></a><a name="bkmk_data_process_progress"></a><span data-ttu-id="37b92-138">Progresso do processo de dados</span><span class="sxs-lookup"><span data-stu-id="37b92-138">Data Process Progress</span></span>  
 <span data-ttu-id="37b92-139">A caixa de diálogo **Progresso do Processo de Dados** o habilita a monitorar o processamento de dados que você importou de uma fonte externa para o modelo.</span><span class="sxs-lookup"><span data-stu-id="37b92-139">The **Data Process Progress** dialog box enables you to monitor the processing of data that you have imported into the model from an external source.</span></span> <span data-ttu-id="37b92-140">Para acessar essa caixa de diálogo, clique no menu **Modelo** , clique em **Processar Partições**, em **Processar Tabela** ou **Processar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="37b92-140">To access this dialog box, click on the **Model** menu, and then click **Process Partitions**, **Process Table** or **Process All**.</span></span>  
  
 <span data-ttu-id="37b92-141">**Status**</span><span class="sxs-lookup"><span data-stu-id="37b92-141">**Status**</span></span>  
 <span data-ttu-id="37b92-142">Indica se a operação de processo foi bem-sucedida ou não.</span><span class="sxs-lookup"><span data-stu-id="37b92-142">Indicates whether the process operation was successful or not.</span></span>  
  
 <span data-ttu-id="37b92-143">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="37b92-143">**Details**</span></span>  
 <span data-ttu-id="37b92-144">Lista as tabelas e as exibições que foram importadas, o número de linhas que foram importadas e fornece um link para um relatório de qualquer problema.</span><span class="sxs-lookup"><span data-stu-id="37b92-144">Lists the tables and views that were imported, the number of rows that were imported, and provides a link to a report of any issues.</span></span>  
  
 <span data-ttu-id="37b92-145">**Parar Atualização**</span><span class="sxs-lookup"><span data-stu-id="37b92-145">**Stop Refresh**</span></span>  
 <span data-ttu-id="37b92-146">Clique para interromper a operação de processo.</span><span class="sxs-lookup"><span data-stu-id="37b92-146">Click to halt the process operation.</span></span> <span data-ttu-id="37b92-147">Essa opção será útil se a operação estiver demorando muito ou se houver muitos erros.</span><span class="sxs-lookup"><span data-stu-id="37b92-147">This option is useful if the operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b92-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="37b92-148">See Also</span></span>  
 <span data-ttu-id="37b92-149">[Processar dados &#40;SSAS de tabela&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="37b92-149">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="37b92-150">Solucionar problemas de dados de processo &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="37b92-150">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)  
  
  
