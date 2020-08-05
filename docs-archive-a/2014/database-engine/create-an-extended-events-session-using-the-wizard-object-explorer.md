---
title: Criar uma sessão de eventos estendidos usando o assistente (Pesquisador de objetos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- Sql12.ssms.XeWizard.Summary.f1
- Sql12.ssms.XeWizard.SetSessionProperties.f1
- Sql12.ssms.XeWizard.CaptureAddFields.f1
- Sql12.ssms.XeWizard.SelectEvents.f1
- Sql12.ssms.XeWizard.SpecifySessionTargets.f1
- Sql12.ssms.XeWizard.Welcome.f1
- sql12.ssms.XeWizard.Welcome.f1
- Sql12.ssms.XeWizard.ChooseTemplate.f1
- Sql12.ssms.XeWizard.SetSessionEventFilters.f1
- Sql12.ssms.XeWizard.Results.f1
helpviewer_keywords:
- Sql11.ssms.XeWizard.CaptureAddFields.f1
- Sql11.ssms.XeWizard.SetSessionEventFilters.f1
- Sql11.ssms.XeWizard.SpecifySessionTargets.f1
- Sql11.ssms.XeWizard.Results.f1
- Sql11.ssms.XeWizard.ChooseTemplate.f1
- Sql11.ssms.XeWizard.SetSessionProperties.f1
- Sql11.ssms.XeWizard.Welcome.f1
- Sql11.ssms.XeWizard.Summary.f1
- Sql11.ssms.XeWizard.SelectEvents.f1
ms.assetid: 80c0456f-17c0-41d8-b2aa-502a2f3bb6de
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfc9141b0b99d5b06fc73044b8f4fae623922b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574258"
---
# <a name="create-an-extended-events-session-using-the-wizard-object-explorer"></a><span data-ttu-id="187a2-102">Criar uma sessão de Eventos Estendidos usando o assistente (Pesquisador de Objetos)</span><span class="sxs-lookup"><span data-stu-id="187a2-102">Create an Extended Events Session Using the Wizard (Object Explorer)</span></span>
  <span data-ttu-id="187a2-103">Para ajudar você a selecionar e capturar eventos no servidor, os Eventos Estendidos incluem um Assistente para Nova Sessão que o guiará pelas etapas de criação de uma sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="187a2-103">To help you select and capture events on your server, Extended Events includes a New Session Wizard that guides you through the steps to create an Extended Events session.</span></span> <span data-ttu-id="187a2-104">O Assistente para Nova Sessão expõe a maioria da funcionalidade de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="187a2-104">The New Session Wizard exposes most of the Extended Events functionality.</span></span> <span data-ttu-id="187a2-105">A caixa de diálogo [Nova Sessão](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) também permite definir uma sessão de Eventos Estendidos que captura, exibe e analisa seus dados.</span><span class="sxs-lookup"><span data-stu-id="187a2-105">The [New Session dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md) also lets you define an Extended Events session that captures, displays, and analyzes your data.</span></span> <span data-ttu-id="187a2-106">A caixa de diálogo Nova Sessão expõe toda a funcionalidade de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="187a2-106">The New Session dialog exposes all Extended Events functionality.</span></span>  
  
### <a name="to-open-the-new-session-wizard"></a><span data-ttu-id="187a2-107">Para abrir o Assistente para Nova Sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-107">To open the New Session Wizard</span></span>  
  
1.  <span data-ttu-id="187a2-108">No Pesquisador de Objetos, expanda o nó **Gerenciamento** e, em seguida, expanda **Eventos Estendidos**.</span><span class="sxs-lookup"><span data-stu-id="187a2-108">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="187a2-109">Clique com o botão direito do mouse em **Sessões** e clique em **Assistente para Nova Sessão**.</span><span class="sxs-lookup"><span data-stu-id="187a2-109">Right-click **Sessions**, and then click **New Session Wizard**.</span></span>  
  
### <a name="use-the-following-new-session-wizard-pages-to-create-an-event-session"></a><span data-ttu-id="187a2-110">Use as seguintes páginas do Assistente para Nova Sessão para criar uma sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-110">Use the following New Session Wizard pages to create an event session</span></span>  
  
-   [<span data-ttu-id="187a2-111">Introdução</span><span class="sxs-lookup"><span data-stu-id="187a2-111">Introduction</span></span>](#BKMK_Welcome)  
  
-   [<span data-ttu-id="187a2-112">Definir Propriedades da Sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-112">Set Session Properties</span></span>](#BKMK_SetSessionProperties)  
  
-   [<span data-ttu-id="187a2-113">Escolher Modelo</span><span class="sxs-lookup"><span data-stu-id="187a2-113">Choose Template</span></span>](#BKMK_ChooseTemplate)  
  
-   [<span data-ttu-id="187a2-114">Selecionar Eventos a Serem Capturados</span><span class="sxs-lookup"><span data-stu-id="187a2-114">Select Events to Capture</span></span>](#BKMK_SelectEventsToCapture)  
  
-   [<span data-ttu-id="187a2-115">Capturar Campos Globais</span><span class="sxs-lookup"><span data-stu-id="187a2-115">Capture Global Fields</span></span>](#BKMK_CaptureGlobalFields)  
  
-   [<span data-ttu-id="187a2-116">Definir Filtros de Eventos de Sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-116">Set Session Event Filters</span></span>](#BKMK_SetSessionEventFilters)  
  
-   [<span data-ttu-id="187a2-117">Especificar Armazenamento de Dados da Sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-117">Specify Session Data Storage</span></span>](#BKMK_SpecifySessionDataOutput)  
  
-   [<span data-ttu-id="187a2-118">Resumo</span><span class="sxs-lookup"><span data-stu-id="187a2-118">Summary</span></span>](#BKMK_Summary)  
  
-   [<span data-ttu-id="187a2-119">Criar Sessão de Evento</span><span class="sxs-lookup"><span data-stu-id="187a2-119">Create Event Session</span></span>](#BKMK_CreateEventSession)  
  
##  <a name="introduction"></a><a name="BKMK_Welcome"></a><span data-ttu-id="187a2-120">Apresentações</span><span class="sxs-lookup"><span data-stu-id="187a2-120">Introduction</span></span>  
 <span data-ttu-id="187a2-121">Na página **Introdução** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-121">On the **Introduction** page, do the following:</span></span>  
  
-   <span data-ttu-id="187a2-122">Na página **Introdução** do Assistente para Nova Sessão, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="187a2-122">On the **Introduction** page of the New Session Wizard, click **Next**.</span></span>  
  
     <span data-ttu-id="187a2-123">Marque a caixa de seleção **Não mostrar esta página novamente** caso pretenda usar o assistente mais de uma vez e não queira ler a introdução cada vez que o assistente for iniciado.</span><span class="sxs-lookup"><span data-stu-id="187a2-123">Select the **Do not show this page again** check box if you will be using the wizard more than once and do not want to read the introduction each time the wizard is launched.</span></span>  
  
##  <a name="set-session-properties"></a><a name="BKMK_SetSessionProperties"></a><span data-ttu-id="187a2-124">Definir propriedades da sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-124">Set Session Properties</span></span>  
 <span data-ttu-id="187a2-125">Na página **Definir Propriedades da Sessão** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-125">On the **Set Session Properties** page, do the following:</span></span>  
  
-   <span data-ttu-id="187a2-126">Na caixa **Nome da sessão** , digite um nome significativo para a sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-126">In the **Session name** box, type a meaningful name for the event session.</span></span>  
  
     <span data-ttu-id="187a2-127">Para iniciar a sessão ao inicializar o servidor, marque a caixa de seleção **Iniciar a sessão de evento na inicialização do servidor** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="187a2-127">If you want to start the session when you start the server, select the **Start the event session at server startup** check box, and then click **Next**.</span></span>  
  
##  <a name="choose-template"></a><a name="BKMK_ChooseTemplate"></a><span data-ttu-id="187a2-128">Escolher modelo</span><span class="sxs-lookup"><span data-stu-id="187a2-128">Choose Template</span></span>  
 <span data-ttu-id="187a2-129">Na página **Escolher Modelo** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-129">On the **Choose Template** page, do the following:</span></span>  
  
-   <span data-ttu-id="187a2-130">Selecione a opção **Usar este modelo de sessão de evento** para selecionar um dos modelos de um conjunto de modelos pré-configurados projetados para problemas comuns.</span><span class="sxs-lookup"><span data-stu-id="187a2-130">Select the **Use this event session template** option to select from a set of pre-configured templates designed for common problems.</span></span> <span data-ttu-id="187a2-131">Selecione o modelo desejado na lista suspensa e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="187a2-131">Select the template you want to use from the drop-down list, and then click **Next**.</span></span>  
  
     <span data-ttu-id="187a2-132">-OU-</span><span class="sxs-lookup"><span data-stu-id="187a2-132">-OR-</span></span>  
  
-   <span data-ttu-id="187a2-133">Selecione a opção **Não usar um modelo** caso não deseje usar nenhum modelo pré-configurado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="187a2-133">Select the **Do not use a template** option if you do not want to use any pre-configured template, and then click **Next**.</span></span>  
  
##  <a name="select-events-to-capture"></a><a name="BKMK_SelectEventsToCapture"></a><span data-ttu-id="187a2-134">Selecionar eventos a serem capturados</span><span class="sxs-lookup"><span data-stu-id="187a2-134">Select Events to Capture</span></span>  
 <span data-ttu-id="187a2-135">Na página **Selecionar Eventos a Serem Capturados** página, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-135">On the **Select Events to Capture** page, do the following:</span></span>  
  
1.  <span data-ttu-id="187a2-136">Selecione os eventos que você deseja capturar na **Biblioteca de eventos**e clique na seta para a direita.</span><span class="sxs-lookup"><span data-stu-id="187a2-136">Select the events you want to capture from the **Event library**, and then click the right arrow.</span></span> <span data-ttu-id="187a2-137">Você pode selecionar vários eventos na Biblioteca de Eventos usando Shift+Clique ou Ctrl+Clique.</span><span class="sxs-lookup"><span data-stu-id="187a2-137">You can select multiple events in the Event Library by using either Shift+Click or Ctrl+Click.</span></span>  
  
     <span data-ttu-id="187a2-138">Na caixa da lista suspensa, você pode especificar como deseja procurar os eventos a serem capturados.</span><span class="sxs-lookup"><span data-stu-id="187a2-138">You can select how you want to search for the events you want to capture from the drop-down list box.</span></span> <span data-ttu-id="187a2-139">Por exemplo, você pode procurar nomes de evento ou nomes de evento e suas descrições.</span><span class="sxs-lookup"><span data-stu-id="187a2-139">For example, you can search for event names or event names and their descriptions.</span></span> <span data-ttu-id="187a2-140">Você pode procurar qualquer palavra na tabela inserindo o texto que deseja procurar na caixa **Biblioteca de eventos** .</span><span class="sxs-lookup"><span data-stu-id="187a2-140">You can search for any word in the table by entering the text you want to search for in the **Event library** box.</span></span> <span data-ttu-id="187a2-141">Por exemplo, se você quiser localizar o evento **lock_acquired** , poderá inserir **Lock**ou **Bloquear aquisição**.</span><span class="sxs-lookup"><span data-stu-id="187a2-141">For example, if you want to find the **lock_acquired** event, you can enter **lock**, or **lock acquire**.</span></span>  
  
     <span data-ttu-id="187a2-142">Os eventos selecionados aparecerão na caixa **Eventos selecionados** .</span><span class="sxs-lookup"><span data-stu-id="187a2-142">The events you select appear in the **Selected events** box.</span></span> <span data-ttu-id="187a2-143">Para remover eventos da caixa **Eventos selecionados** , clique na seta para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="187a2-143">To remove events from the **Selected events** box, click the left arrow.</span></span>  
  
2.  <span data-ttu-id="187a2-144">Depois que você selecionar os eventos a serem capturados, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="187a2-144">After you select the events you want to capture, click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="187a2-145">Os eventos do canal de **Depuração** são ocultos por padrão.</span><span class="sxs-lookup"><span data-stu-id="187a2-145">Events from the **Debug** channel are hidden by default.</span></span> <span data-ttu-id="187a2-146">Para exibir os eventos de depuração, selecione **Depurar** na lista suspensa **Canal** .</span><span class="sxs-lookup"><span data-stu-id="187a2-146">To display debug events, select **Debug** from the **Channel** drop-down list.</span></span>  
  
##  <a name="capture-global-fields"></a><a name="BKMK_CaptureGlobalFields"></a><span data-ttu-id="187a2-147">Capturar campos globais</span><span class="sxs-lookup"><span data-stu-id="187a2-147">Capture Global Fields</span></span>  
 <span data-ttu-id="187a2-148">Você usa campos globais (também denominados ações) para associar uma ou várias ações a seus eventos selecionados.</span><span class="sxs-lookup"><span data-stu-id="187a2-148">You use global fields (also referred to as actions) to associate single or multiple actions for your selected events.</span></span> <span data-ttu-id="187a2-149">Se você selecionou um modelo na página **Escolher Modelo** , todos os campos globais definidos no modelo serão exibidos nesta página.</span><span class="sxs-lookup"><span data-stu-id="187a2-149">If you selected a template on the **Choose Template** page, all of the global fields that are defined in the template are displayed on this page.</span></span>  
  
 <span data-ttu-id="187a2-150">Na página **Capturar Campos Globais** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-150">On the **Capture Global Fields** page, do the following:</span></span>  
  
-   <span data-ttu-id="187a2-151">Selecione os campos globais que você deseja capturar para a sessão de evento e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="187a2-151">Select the global fields that you want to capture for the event session, and then click **Next**.</span></span>  
  
     <span data-ttu-id="187a2-152">Você pode remover ou adicionar campos globais marcando ou desmarcando a caixa de seleção ao lado do campo global.</span><span class="sxs-lookup"><span data-stu-id="187a2-152">You can remove or add global fields by selecting or clearing the check box next to the global field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="187a2-153">As ações selecionadas são classificadas por **Nome** , permitindo que você exiba as ações associadas em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="187a2-153">The selected actions are sorted by **Name** enabling you to view the associated actions in alphabetical order.</span></span> <span data-ttu-id="187a2-154">Você pode realizar a classificação por descrição ou pelo status habilitar/desabilitar clicando no título de coluna ao lado do nome de campo.</span><span class="sxs-lookup"><span data-stu-id="187a2-154">You can sort by description or by the enable/disable status by clicking the column heading next to the field name.</span></span>  
  
##  <a name="set-session-event-filters"></a><a name="BKMK_SetSessionEventFilters"></a><span data-ttu-id="187a2-155">Definir filtros de eventos de sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-155">Set Session Event Filters</span></span>  
 <span data-ttu-id="187a2-156">Você pode aplicar filtros (também denominados predicados) para limitar os eventos a serem capturados.</span><span class="sxs-lookup"><span data-stu-id="187a2-156">You can apply filters (also called predicates) to limit the events that you want to capture.</span></span> <span data-ttu-id="187a2-157">Na página **Definir Filtros de Eventos de Sessão** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-157">On the **Set Session Event Filters** page, do the following:</span></span>  
  
1.  <span data-ttu-id="187a2-158">Se você não estiver usando um modelo pré-configurado, crie seus critérios de filtro e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="187a2-158">If you are not using a pre-configured template, create your filter criteria, and then click **Next**.</span></span>  
  
     <span data-ttu-id="187a2-159">Se você estiver usando um modelo pré-configurado, na seção **Filtros do modelo (somente leitura)** , o Assistente para Nova Sessão listará os filtros já criados com base no modelo.</span><span class="sxs-lookup"><span data-stu-id="187a2-159">If you are using a pre-configured template, in the **Filters from template (read-only)** section, the New Session Wizard lists filters already created from the template.</span></span>  
  
2.  <span data-ttu-id="187a2-160">Na seção **Filtros adicionais** , você pode configurar filtros adicionais para a sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-160">In the **Additional filters** section, you can configure additional filters for the event session.</span></span>  
  
     <span data-ttu-id="187a2-161">Os filtros que você configura se aplicam a todos os eventos selecionados.</span><span class="sxs-lookup"><span data-stu-id="187a2-161">The filters you configure apply to all selected events.</span></span> <span data-ttu-id="187a2-162">O Assistente para Nova Sessão não oferece suporte à configuração de filtros para cada evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-162">The New Session Wizard does not support configuring filters for each event.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="187a2-163">Quando você configurar uma cláusula de grupo para o filtro, serão removidos os parênteses redundantes do filtro depois que o resultado for salvo.</span><span class="sxs-lookup"><span data-stu-id="187a2-163">When you configure a group clause for your filter, redundant parentheses are removed from the filter after the result is saved.</span></span> <span data-ttu-id="187a2-164">Por exemplo, se você criar um agrupamento de filtros **Cláusula 1** e **Cláusula 2**, aparecerão parênteses delimitando as cláusulas.</span><span class="sxs-lookup"><span data-stu-id="187a2-164">For example, if you create a filter grouping **Clause 1** and **Clause 2**, parentheses will appear around the clauses.</span></span> <span data-ttu-id="187a2-165">Depois que você salvar o filtro, os parênteses redundantes serão removidos.</span><span class="sxs-lookup"><span data-stu-id="187a2-165">After you save the filter, the redundant parentheses are removed.</span></span> <span data-ttu-id="187a2-166">A remoção dos parênteses não afetará a lógica do filtro.</span><span class="sxs-lookup"><span data-stu-id="187a2-166">The removal of the parentheses does not affect the filter logic.</span></span>  
  
##  <a name="specify-session-data-storage"></a><a name="BKMK_SpecifySessionDataOutput"></a><span data-ttu-id="187a2-167">Especificar o armazenamento de dados da sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-167">Specify Session Data Storage</span></span>  
 <span data-ttu-id="187a2-168">Use a página **Especificar Armazenamento de Dados da Sessão** para especificar como coletar os dados para análise.</span><span class="sxs-lookup"><span data-stu-id="187a2-168">You use the **Specify Session Data Storage** page to specify how you want to collect your data for analysis.</span></span> <span data-ttu-id="187a2-169">Os Eventos Estendidos do SQL Server usam destinos para saída de dados.</span><span class="sxs-lookup"><span data-stu-id="187a2-169">SQL Server Extended Events uses targets for data output.</span></span> <span data-ttu-id="187a2-170">Os destinos armazenam dados de evento e podem executar ações como gravar um arquivo e agregar dados de evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-170">Targets store event data and can perform actions such as writing to a file and aggregating event data.</span></span> <span data-ttu-id="187a2-171">Especifique como coletar os dados para análise e, na página **Especificar Armazenamento de Dados da Sessão** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-171">Decide how you want to collect your data for analysis, and on the **Specify Session Data Storage** page, do the following:</span></span>  
  
1.  <span data-ttu-id="187a2-172">Para conjuntos de dados grandes e registros históricos de criação, marque a caixa de seleção **Salvar dados em um arquivo para análise posterior** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-172">For large data sets and creating historical records, select the **Save data to a file for later analysis** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="187a2-173">Na caixa **Nome do arquivo no servidor** , insira o caminho e o nome do arquivo ou clique em **Procurar** para especificar o diretório de arquivos no servidor onde você deseja salvar os dados.</span><span class="sxs-lookup"><span data-stu-id="187a2-173">In the **File name on server** box, enter the path and file name, or click **Browse** to specify the file directory on the server where you want to save the data.</span></span>  
  
    2.  <span data-ttu-id="187a2-174">Na caixa **Tamanho máximo de arquivo** , especifique um tamanho máximo de arquivo a ser usado como destino do arquivo.</span><span class="sxs-lookup"><span data-stu-id="187a2-174">In the **Maximum file size** box, specify the maximum file size to be used for the file target.</span></span> <span data-ttu-id="187a2-175">Se você não especificar o tamanho máximo do arquivo, este crescerá até que o disco fique cheio.</span><span class="sxs-lookup"><span data-stu-id="187a2-175">If you do not specify the maximum file size, the file will grow until the disk is full.</span></span> <span data-ttu-id="187a2-176">O tamanho de arquivo padrão é 1 GB (gigabyte).</span><span class="sxs-lookup"><span data-stu-id="187a2-176">The default file size is 1 gigabyte (GB).</span></span>  
  
    3.  <span data-ttu-id="187a2-177">Marque a caixa de seleção **Habilitar substituição de arquivo** para habilitar a substituição de arquivo para o destino de arquivo.</span><span class="sxs-lookup"><span data-stu-id="187a2-177">Select the **Enable file rollover** check box to enable file rollover for the file target.</span></span>  
  
    4.  <span data-ttu-id="187a2-178">Na caixa **Número máximo de arquivo** , especifique o número máximo de arquivos a ser retido no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="187a2-178">In the **Maximum number of files** box, specify the maximum number of files you want to retain in the file system.</span></span>  
  
2.  <span data-ttu-id="187a2-179">Para coletar dados recentes, marque a caixa de seleção **Trabalhar somente com os dados mais recentes (destino do buffer de anéis)** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-179">For collecting recent data, select the **Work with only the most recent data (ring buffer target)** check box, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="187a2-180">Na caixa **Número de eventos a serem mantidos** , insira ou selecione o número de eventos que deseja manter usando as setas para cima e para baixo.</span><span class="sxs-lookup"><span data-stu-id="187a2-180">In the **Number of events to keep** box, enter or select the number of events you want to keep by using the up and down arrows.</span></span>  
  
    2.  <span data-ttu-id="187a2-181">Na caixa **Tamanho máximo da memória do buffer** , especifique a quantidade máxima de memória de buffer a ser usada.</span><span class="sxs-lookup"><span data-stu-id="187a2-181">In the **Maximum buffer memory size** box, specify the maximum amount of buffer memory to use.</span></span> <span data-ttu-id="187a2-182">Os eventos existentes são removidos quando esse valor é atingido.</span><span class="sxs-lookup"><span data-stu-id="187a2-182">The existing events are dropped when this value is reached.</span></span>  
  
    3.  <span data-ttu-id="187a2-183">Se você desejar manter um número específico de eventos de cada tipo no buffer, marque a caixa de seleção **Manter um número específico de eventos (por tipo) quando o buffer estiver cheio** .</span><span class="sxs-lookup"><span data-stu-id="187a2-183">If you want to keep a specific number of events of each type in the buffer, select the **Keep a specified number of events (per type) when the buffer is full** check box.</span></span>  
  
    4.  <span data-ttu-id="187a2-184">Na caixa **Número de eventos a serem mantidos (por tipo)** , insira ou selecione o número de eventos (por tipo) que deseja manter usando as setas para cima e para baixo.</span><span class="sxs-lookup"><span data-stu-id="187a2-184">In the **Number of events to keep (per type)** box, enter or select the number of events (per type) that you want to keep by using the up and down arrows.</span></span>  
  
##  <a name="summary"></a><a name="BKMK_Summary"></a> <span data-ttu-id="187a2-185">Resumo</span><span class="sxs-lookup"><span data-stu-id="187a2-185">Summary</span></span>  
 <span data-ttu-id="187a2-186">Na página **Resumo** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-186">On the **Summary** page, do the following:</span></span>  
  
1.  <span data-ttu-id="187a2-187">Verifique se suas seleções estão corretas.</span><span class="sxs-lookup"><span data-stu-id="187a2-187">Make sure that your selections are correct.</span></span> <span data-ttu-id="187a2-188">Expanda os nós de sessão de evento para verificar se todas as seleções serão incluídas na sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-188">Expand the event session nodes to verify that all of your selections will be included in the event session.</span></span>  
  
2.  <span data-ttu-id="187a2-189">Clique em **Script** para exportar o script de criação de sessão para uma nova janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="187a2-189">Click **Script** to export the session creation script to a new Query Editor window.</span></span>  
  
3.  <span data-ttu-id="187a2-190">Clique em **Concluir** para criar a sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-190">Click **Finish** to create the event session.</span></span>  
  
##  <a name="create-event-session"></a><a name="BKMK_CreateEventSession"></a><span data-ttu-id="187a2-191">Criar sessão de evento</span><span class="sxs-lookup"><span data-stu-id="187a2-191">Create Event Session</span></span>  
 <span data-ttu-id="187a2-192">Na página **Criar Sessão de Evento** , depois que a sessão de evento for criada, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="187a2-192">On the **Create Event Session** page, after your event session has been successfully created, do the following:</span></span>  
  
1.  <span data-ttu-id="187a2-193">Clique em **Iniciar a sessão de evento imediatamente após a criação da sessão** para iniciar a sessão depois que você fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="187a2-193">Click **Start the event session immediately after session creation** to start the session after you close the wizard.</span></span> <span data-ttu-id="187a2-194">Você deve iniciar a sessão de evento imediatamente após a criação da sessão para que possa observar os dados dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="187a2-194">You must start the event session immediately after you create the session to be able to watch live data.</span></span>  
  
2.  <span data-ttu-id="187a2-195">Clique em **Observar dados dinâmicos na tela à medida que eles são capturados** para exibir os dados dinâmicos da sua sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="187a2-195">Click **Watch live data on screen as it is captured** to view live data for your event session.</span></span> <span data-ttu-id="187a2-196">Os dados dinâmicos começarão a exibir o rastreamento imediatamente depois que a sessão for criada.</span><span class="sxs-lookup"><span data-stu-id="187a2-196">The live data will start displaying tracing immediately after the session is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="187a2-197">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="187a2-197">See Also</span></span>  
 [<span data-ttu-id="187a2-198">Criar uma sessão de Eventos Estendidos usando a caixa de diálogo Nova Sessão</span><span class="sxs-lookup"><span data-stu-id="187a2-198">Create an Extended Events Session Using the New Session Dialog</span></span>](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md)  
  
  
