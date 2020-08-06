---
title: Propriedades do rastreamento (guia geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.general.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: 25227268-143b-477e-aac9-8268bcaf2078
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 30de30c88db35a41f8f118b6545d56a78b2dec79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685254"
---
# <a name="trace-properties-general-tab"></a><span data-ttu-id="8218f-102">Propriedades do Rastreamento (guia Geral)</span><span class="sxs-lookup"><span data-stu-id="8218f-102">Trace Properties (General Tab)</span></span>
  <span data-ttu-id="8218f-103">Use a guia **Geral** da caixa de diálogo **Propriedades do Rastreamento** para exibir ou especificar propriedades de um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8218f-103">Use the **General** tab of the **Trace Properties** dialog box to view or specify properties of a trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8218f-104">Opções</span><span class="sxs-lookup"><span data-stu-id="8218f-104">Options</span></span>  
 <span data-ttu-id="8218f-105">**Nome do rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8218f-105">**Trace name**</span></span>  
 <span data-ttu-id="8218f-106">Especifique o nome do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8218f-106">Specify the name of the trace.</span></span>  
  
 <span data-ttu-id="8218f-107">**Nome do provedor de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8218f-107">**Trace provider name**</span></span>  
 <span data-ttu-id="8218f-108">Exibe o nome da instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que será rastreada.</span><span class="sxs-lookup"><span data-stu-id="8218f-108">Shows the name of the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that will be traced.</span></span> <span data-ttu-id="8218f-109">Esse campo é populado automaticamente com o nome do servidor que você especificou ao se conectar.</span><span class="sxs-lookup"><span data-stu-id="8218f-109">This field is populated automatically with the name of the server that you specified when you connected.</span></span> <span data-ttu-id="8218f-110">Para alterar o nome do provedor de rastreamento, clique em **Cancelar** para fechar a caixa de diálogo e iniciar um novo rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8218f-110">To change the name of the trace provider, click **Cancel** to close the dialog box, and start a new trace.</span></span>  
  
 <span data-ttu-id="8218f-111">**Tipo de provedor de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8218f-111">**Trace provider type**</span></span>  
 <span data-ttu-id="8218f-112">Exibe o tipo de servidor que está fornecendo o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8218f-112">Shows the server type that is providing the trace.</span></span> <span data-ttu-id="8218f-113">O arquivo de definição de rastreamento popula o campo **Tipo de provedor de rastreamento** automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8218f-113">The trace definition file populates the **Trace provider type** field automatically.</span></span> <span data-ttu-id="8218f-114">Não é possível modificar esse campo.</span><span class="sxs-lookup"><span data-stu-id="8218f-114">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="8218f-115">**version**</span><span class="sxs-lookup"><span data-stu-id="8218f-115">**version**</span></span>  
 <span data-ttu-id="8218f-116">Exibe a versão do servidor que está fornecendo o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8218f-116">Shows the version of the server that is providing the trace.</span></span> <span data-ttu-id="8218f-117">O arquivo de definição de rastreamento popula o campo **Versão** automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8218f-117">The trace definition file populates the **Version** field automatically.</span></span> <span data-ttu-id="8218f-118">Não é possível modificar esse campo.</span><span class="sxs-lookup"><span data-stu-id="8218f-118">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="8218f-119">**Usar o modelo**</span><span class="sxs-lookup"><span data-stu-id="8218f-119">**Use the template**</span></span>  
 <span data-ttu-id="8218f-120">Selecione um modelo do diretório modelo.</span><span class="sxs-lookup"><span data-stu-id="8218f-120">Select a template from the template directory.</span></span> <span data-ttu-id="8218f-121">O diretório é populado com os modelos padrões e qualquer modelo definido pelo usuário, criados para o tipo de provedor de rastreamento atual.</span><span class="sxs-lookup"><span data-stu-id="8218f-121">The directory is populated with the default templates and any user-defined templates created for the current trace provider type.</span></span>  
  
 <span data-ttu-id="8218f-122">**Salvar no arquivo**</span><span class="sxs-lookup"><span data-stu-id="8218f-122">**Save to file**</span></span>  
 <span data-ttu-id="8218f-123">Capture os dados de rastreamento para um arquivo .trc.</span><span class="sxs-lookup"><span data-stu-id="8218f-123">Capture the trace data to a .trc file.</span></span> <span data-ttu-id="8218f-124">Salvar dados de rastreamento é útil para revisão e análise posteriores.</span><span class="sxs-lookup"><span data-stu-id="8218f-124">Saving trace data is useful for later review and analysis.</span></span>  
  
 <span data-ttu-id="8218f-125">**Definir tamanho máximo do arquivo (MB)**</span><span class="sxs-lookup"><span data-stu-id="8218f-125">**Set maximum file size (MB)**</span></span>  
 <span data-ttu-id="8218f-126">Se você optar por salvar os dados de rastreamento em um arquivo, especifique o tamanho máximo do arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8218f-126">If you choose to save the trace data to a file, you must specify the maximum size of the trace file.</span></span> <span data-ttu-id="8218f-127">O padrão é 5 MB (megabytes).</span><span class="sxs-lookup"><span data-stu-id="8218f-127">The default is 5 megabytes (MB).</span></span> <span data-ttu-id="8218f-128">O tamanho máximo é limitado somente pelo sistema de arquivos (NTFS, FAT) onde o arquivo é salvo.</span><span class="sxs-lookup"><span data-stu-id="8218f-128">The maximum size is limited only by the file system (NTFS, FAT) where the file is saved.</span></span>  
  
 <span data-ttu-id="8218f-129">\<Graphic>**Salvar como**</span><span class="sxs-lookup"><span data-stu-id="8218f-129">\<Graphic> **Save As**</span></span>  
 <span data-ttu-id="8218f-130">Depois de selecionar para salvar, é possível selecionar esse ícone para alterar o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8218f-130">After you have selected to save, you can select this icon to change the file name.</span></span>  
  
 <span data-ttu-id="8218f-131">**Habilitar substituição de arquivo**</span><span class="sxs-lookup"><span data-stu-id="8218f-131">**Enable file rollover**</span></span>  
 <span data-ttu-id="8218f-132">Selecione para habilitar a criação de arquivos adicionais para aceitar os dados de rastreamento, quando o tamanho máximo de arquivo for atingido.</span><span class="sxs-lookup"><span data-stu-id="8218f-132">Select to enable the creation of additional files to accept the trace data when the maximum file size is reached.</span></span> <span data-ttu-id="8218f-133">Cada nome de arquivo novo consiste do nome de arquivo .trc original, numerado em sequência.</span><span class="sxs-lookup"><span data-stu-id="8218f-133">Each new file name consists of the original .trc file name, numbered sequentially.</span></span> <span data-ttu-id="8218f-134">Por exemplo, ao alcançar o tamanho máximo do arquivo, **NewTrace.trc** é fechado e um novo arquivo **NewTrace_1.trc**é aberto, seguido de **NewTrace_2.trc**e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8218f-134">For example, once it reaches maximum file size, **NewTrace.trc** closes, and a new file, **NewTrace_1.trc**, opens, followed by **NewTrace_2.trc**, and so on.</span></span> <span data-ttu-id="8218f-135">A substituição de arquivos é habilitada por padrão quando você salvar um rastreamento em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8218f-135">File rollover is enabled by default when you save a trace to a file.</span></span>  
  
 <span data-ttu-id="8218f-136">**Dados de rastreamento de processos do servidor**</span><span class="sxs-lookup"><span data-stu-id="8218f-136">**Server processes trace data**</span></span>  
 <span data-ttu-id="8218f-137">Especifique que o servidor que executa o rastreamento deve processar os dados de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8218f-137">Specify that the server running the trace should process the trace data.</span></span> <span data-ttu-id="8218f-138">Usando essa opção a sobrecarga de desempenho devido ao rastreamento é reduzida.</span><span class="sxs-lookup"><span data-stu-id="8218f-138">Using this option reduces the performance overhead incurred by tracing.</span></span> <span data-ttu-id="8218f-139">Se selecionada, nenhum evento é ignorado mesmo sob condições de tensão.</span><span class="sxs-lookup"><span data-stu-id="8218f-139">If selected, no events are skipped even under stress conditions.</span></span> <span data-ttu-id="8218f-140">Se essa caixa de seleção for desmarcada, o processamento será executado pelo SQL Server Profiler, e há uma possibilidade de que alguns eventos não sejam rastreados sob condições de tensão.</span><span class="sxs-lookup"><span data-stu-id="8218f-140">If this check box is cleared, processing is performed by SQL Server Profiler, and there is a possibility that some events are not traced under stress conditions.</span></span>  
  
 <span data-ttu-id="8218f-141">**Salvar na tabela**</span><span class="sxs-lookup"><span data-stu-id="8218f-141">**Save to table**</span></span>  
 <span data-ttu-id="8218f-142">Capture os dados de rastreamento para uma tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8218f-142">Capture the trace data to a database table.</span></span> <span data-ttu-id="8218f-143">Salvar dados de rastreamento é útil para revisão e análise posteriores.</span><span class="sxs-lookup"><span data-stu-id="8218f-143">Saving trace data is useful for later review and analysis.</span></span> <span data-ttu-id="8218f-144">Entretanto, ao salvar dados de rastreamento para uma tabela isso pode levar a uma sobrecarga significativa no servidor no qual o rastreamento está sendo salvo.</span><span class="sxs-lookup"><span data-stu-id="8218f-144">However, saving trace data to a table can incur significant overhead on the server where the trace is being saved.</span></span> <span data-ttu-id="8218f-145">Se possível, não salve a tabela de rastreamento no mesmo servidor que está sendo rastreado.</span><span class="sxs-lookup"><span data-stu-id="8218f-145">If possible, do not save the trace table on the same server that is being traced.</span></span>  
  
 <span data-ttu-id="8218f-146">\<Graphic>**Tabela de destino**</span><span class="sxs-lookup"><span data-stu-id="8218f-146">\<Graphic> **Destination Table**</span></span>  
 <span data-ttu-id="8218f-147">Depois de selecionar para salvar os dados de rastreamento para uma tabela de banco de dados, é possível selecionar esse ícone para alterar o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="8218f-147">After you have selected to save the trace data to a database table, you can select this icon to change the table name.</span></span>  
  
 <span data-ttu-id="8218f-148">**Definir máximo de linhas (em milhares)**</span><span class="sxs-lookup"><span data-stu-id="8218f-148">**Set maximum rows (in thousands)**</span></span>  
 <span data-ttu-id="8218f-149">Especifique o número maior de linhas nas quais salvar dados.</span><span class="sxs-lookup"><span data-stu-id="8218f-149">Specify the largest number of rows in which to save data.</span></span> <span data-ttu-id="8218f-150">O padrão é 1000 linhas.</span><span class="sxs-lookup"><span data-stu-id="8218f-150">The default is 1000 rows.</span></span>  
  
 <span data-ttu-id="8218f-151">**Habilitar horário de parada do rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8218f-151">**Enable trace stop time**</span></span>  
 <span data-ttu-id="8218f-152">Defina a data e hora para o rastreamento ser concluído e se fechar.</span><span class="sxs-lookup"><span data-stu-id="8218f-152">Set the date and time for the trace to end and close itself.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8218f-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8218f-153">See Also</span></span>  
 [<span data-ttu-id="8218f-154">Criar um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="8218f-154">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
