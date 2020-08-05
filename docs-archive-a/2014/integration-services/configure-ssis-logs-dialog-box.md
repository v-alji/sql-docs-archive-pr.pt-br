---
title: Caixa de diálogo Configurar Logs do SSIS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configuredtslogs.loggingdetails.f1
- sql12.dts.designer.configuredtslogs.providersandlogs.f1
- sql12.dts.designer.configuredtslogs.containers.f1
helpviewer_keywords:
- Configure SSIS Logs dialog box
ms.assetid: 4b980275-cd9a-4943-8c36-727d51f9a484
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 252b45765fb784790bcca0fb86e2e56e7e7baddc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572636"
---
# <a name="configure-ssis-logs-dialog-box"></a><span data-ttu-id="04840-102">caixa de diálogo Configurar Logs do SSIS</span><span class="sxs-lookup"><span data-stu-id="04840-102">Configure SSIS Logs Dialog Box</span></span>
  <span data-ttu-id="04840-103">Use a caixa de diálogo **Configurar Logs de SSIS** para definir as opções do log para um pacote.</span><span class="sxs-lookup"><span data-stu-id="04840-103">Use the **Configure SSIS Logs** dialog box to define logging options for a package.</span></span>  
  
 <span data-ttu-id="04840-104">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="04840-104">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="04840-105">Abrir a caixa de diálogo Configurar Logs de SSIS</span><span class="sxs-lookup"><span data-stu-id="04840-105">Open the Configure SSIS Logs Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="04840-106">Configurar as opções no painel Contêineres</span><span class="sxs-lookup"><span data-stu-id="04840-106">Configure the Options in the Containers Pane</span></span>](#container)  
  
3.  [<span data-ttu-id="04840-107">Configurar as opções na guia Provedores e Logs</span><span class="sxs-lookup"><span data-stu-id="04840-107">Configure the Options on the Providers and Logs Tab</span></span>](#provider)  
  
4.  [<span data-ttu-id="04840-108">Configurar as opções na guia Detalhes</span><span class="sxs-lookup"><span data-stu-id="04840-108">Configure the Options on the Details Tab</span></span>](#detail)  
  
##  <a name="open-the-configure-ssis-logs-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="04840-109">Abrir a caixa de diálogo Configurar Logs de SSIS</span><span class="sxs-lookup"><span data-stu-id="04840-109">Open the Configure SSIS Logs Dialog Box</span></span>  
 <span data-ttu-id="04840-110">**Para abrir a caixa de diálogo Configurar Logs de SSIS**</span><span class="sxs-lookup"><span data-stu-id="04840-110">**To open the Configure SSIS Logs dialog box**</span></span>  
  
-   <span data-ttu-id="04840-111">No [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, clique em **Log** no menu **SSIS** .</span><span class="sxs-lookup"><span data-stu-id="04840-111">In the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click **Logging** on the **SSIS** menu.</span></span>  
  
##  <a name="configure-the-options-in-the-containers-pane"></a><a name="container"></a> <span data-ttu-id="04840-112">Configurar as opções no painel Contêineres</span><span class="sxs-lookup"><span data-stu-id="04840-112">Configure the Options in the Containers Pane</span></span>  
 <span data-ttu-id="04840-113">Use o painel **Contêineres** da caixa de diálogo **Configurar Logs do SSIS** para habilitar o pacote e seus contêineres para logs.</span><span class="sxs-lookup"><span data-stu-id="04840-113">Use the **Containers** pane of the **Configure SSIS Logs** dialog box to enable the package and its containers for logging.</span></span>  
  
### <a name="options"></a><span data-ttu-id="04840-114">Opções</span><span class="sxs-lookup"><span data-stu-id="04840-114">Options</span></span>  
 <span data-ttu-id="04840-115">**Contêineres**</span><span class="sxs-lookup"><span data-stu-id="04840-115">**Containers**</span></span>  
 <span data-ttu-id="04840-116">Marque as caixas de seleção na exibição hierárquica para ativar o pacote e seus contêineres para logs:</span><span class="sxs-lookup"><span data-stu-id="04840-116">Select the check boxes in the hierarchical view to enable the package and its containers for logging:</span></span>  
  
-   <span data-ttu-id="04840-117">Se elas não forem marcadas, o contêiner não será ativado para logs.</span><span class="sxs-lookup"><span data-stu-id="04840-117">If cleared, the container is not enabled for logging.</span></span> <span data-ttu-id="04840-118">Selecione-as para ativar os logs.</span><span class="sxs-lookup"><span data-stu-id="04840-118">Select to enable logging.</span></span>  
  
-   <span data-ttu-id="04840-119">Quando esmaecido, o contêiner usa as opções de log pai.</span><span class="sxs-lookup"><span data-stu-id="04840-119">If dimmed, the container uses the logging options of its parent.</span></span> <span data-ttu-id="04840-120">Esta opção não está disponível para o pacote.</span><span class="sxs-lookup"><span data-stu-id="04840-120">This option is not available for the package.</span></span>  
  
-   <span data-ttu-id="04840-121">Quando marcado, o contêiner define suas próprias opções de log.</span><span class="sxs-lookup"><span data-stu-id="04840-121">If checked, the container defines its own logging options.</span></span>  
  
 <span data-ttu-id="04840-122">Se um contêiner estiver esmaecido e você quiser definir as opções de log no contêiner, clique duas vezes em sua caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="04840-122">If a container is dimmed and you want to set logging options on the container, click its check box twice.</span></span> <span data-ttu-id="04840-123">O primeiro clique apaga a caixa de seleção e o segundo clique a seleciona, permitindo escolher os provedores de log que serão usados e selecionar as informações que serão registradas.</span><span class="sxs-lookup"><span data-stu-id="04840-123">The first click clears the check box, and the second click selects it, enabling you to choose the log providers to use and select the information to log.</span></span>  
  
##  <a name="configure-the-options-on-the-providers-and-logs-tab"></a><a name="provider"></a> <span data-ttu-id="04840-124">Configurar as opções na guia Provedores e Logs</span><span class="sxs-lookup"><span data-stu-id="04840-124">Configure the Options on the Providers and Logs Tab</span></span>  
 <span data-ttu-id="04840-125">Use a guia **Provedores e Logs** da caixa de diálogo **Configurar Logs do SSIS** para criar e configurar logs para a captura de eventos do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="04840-125">Use the **Providers and Logs** tab of the **Configure SSIS Logs** dialog box to create and configure logs for capturing run-time events.</span></span>  
  
### <a name="options"></a><span data-ttu-id="04840-126">Opções</span><span class="sxs-lookup"><span data-stu-id="04840-126">Options</span></span>  
 <span data-ttu-id="04840-127">**Tipo de provedor**</span><span class="sxs-lookup"><span data-stu-id="04840-127">**Provider type**</span></span>  
 <span data-ttu-id="04840-128">Selecione um tipo de provedor de log da lista.</span><span class="sxs-lookup"><span data-stu-id="04840-128">Select a type of log provider from the list.</span></span>  
  
 <span data-ttu-id="04840-129">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="04840-129">**Add**</span></span>  
 <span data-ttu-id="04840-130">Adicione um log do tipo especificado à coleção de provedores de log do pacote.</span><span class="sxs-lookup"><span data-stu-id="04840-130">Add a log of the specified type to the collection of log providers of the package.</span></span>  
  
 <span data-ttu-id="04840-131">**Nome**</span><span class="sxs-lookup"><span data-stu-id="04840-131">**Name**</span></span>  
 <span data-ttu-id="04840-132">Habilite ou desabilite logs para contêineres ou tarefas selecionadas no painel **Contêineres** da caixa de diálogo **Configurar Logs do SSIS** usando as caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="04840-132">Enable or disable logs for containers or tasks selected in the **Containers** pane of the **Configure SSIS Logs** dialog box, by using the check boxes.</span></span> <span data-ttu-id="04840-133">O campo de nome é editável.</span><span class="sxs-lookup"><span data-stu-id="04840-133">The name field is editable.</span></span> <span data-ttu-id="04840-134">Use o nome padrão para o provedor ou digite um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="04840-134">Use the default name for the provider, or type a unique descriptive name.</span></span>  
  
 <span data-ttu-id="04840-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="04840-135">**Description**</span></span>  
 <span data-ttu-id="04840-136">O campo de descrição é editável.</span><span class="sxs-lookup"><span data-stu-id="04840-136">The description field is editable.</span></span> <span data-ttu-id="04840-137">Clique e modifique a descrição padrão do log.</span><span class="sxs-lookup"><span data-stu-id="04840-137">Click and then modify the default description of the log.</span></span>  
  
 <span data-ttu-id="04840-138">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="04840-138">**Configuration**</span></span>  
 <span data-ttu-id="04840-139">Selecione um gerenciador de conexões existente na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="04840-139">Select an existing connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span> <span data-ttu-id="04840-140">Dependendo do tipo de provedor de log, você poderá configurar um gerenciador de conexões OLE DB ou um gerenciador de conexões Arquivo.</span><span class="sxs-lookup"><span data-stu-id="04840-140">Depending on the type of log provider, you can configure an OLE DB connection manager or a File connection manager.</span></span> <span data-ttu-id="04840-141">O provedor de log do [!INCLUDE[msCoName](../includes/msconame-md.md)] Log de Eventos do Windows não requer conexão.</span><span class="sxs-lookup"><span data-stu-id="04840-141">The log provider for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Event Log requires no connection.</span></span>  
  
 <span data-ttu-id="04840-142">Tópicos relacionados: [Gerenciador de conexões OLE DB](connection-manager/ole-db-connection-manager.md) , [Gerenciador de Conexões de Arquivos](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="04840-142">Related Topics: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) manager, [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
 <span data-ttu-id="04840-143">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="04840-143">**Delete**</span></span>  
 <span data-ttu-id="04840-144">Selecione um provedor de log e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="04840-144">Select a log provider and then click **Delete**.</span></span>  
  
##  <a name="configure-the-options-on-the-details-tab"></a><a name="detail"></a> <span data-ttu-id="04840-145">Configurar as opções na guia Detalhes</span><span class="sxs-lookup"><span data-stu-id="04840-145">Configure the Options on the Details Tab</span></span>  
 <span data-ttu-id="04840-146">Use a guia **Detalhes** da caixa de diálogo **Configurar Logs do SSIS** para especificar eventos e detalhes informativos a serem habilitados para log.</span><span class="sxs-lookup"><span data-stu-id="04840-146">Use the **Details** tab of the **Configure SSIS Logs** dialog box to specify the events to enable for logging and the information details to log.</span></span> <span data-ttu-id="04840-147">As informações selecionadas se aplicam a todos os provedores de logs no pacote.</span><span class="sxs-lookup"><span data-stu-id="04840-147">The information that you select applies to all the log providers in the package.</span></span> <span data-ttu-id="04840-148">Por exemplo, você não pode gravar determinadas informações na instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e informações diferentes em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="04840-148">For example, you cannot write some information to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and different information to a text file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="04840-149">Opções</span><span class="sxs-lookup"><span data-stu-id="04840-149">Options</span></span>  
 <span data-ttu-id="04840-150">**Eventos**</span><span class="sxs-lookup"><span data-stu-id="04840-150">**Events**</span></span>  
 <span data-ttu-id="04840-151">Ative ou desative eventos para log.</span><span class="sxs-lookup"><span data-stu-id="04840-151">Enable or disable events for logging.</span></span>  
  
 <span data-ttu-id="04840-152">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="04840-152">**Description**</span></span>  
 <span data-ttu-id="04840-153">Exiba uma descrição do evento.</span><span class="sxs-lookup"><span data-stu-id="04840-153">View a description of the event.</span></span>  
  
 <span data-ttu-id="04840-154">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="04840-154">**Advanced**</span></span>  
 <span data-ttu-id="04840-155">Marque ou desmarque os eventos para log e marque ou desmarque informações que serão usadas no log de cada evento.</span><span class="sxs-lookup"><span data-stu-id="04840-155">Select or clear events to log, and select or clear information to log for each event.</span></span> <span data-ttu-id="04840-156">Clique em **Básico** para ocultar todos os detalhes de log, exceto a lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="04840-156">Click **Basic** to hide all logging details, except the list of events.</span></span> <span data-ttu-id="04840-157">As informações a seguir estão disponíveis para log:</span><span class="sxs-lookup"><span data-stu-id="04840-157">The following information is available for logging:</span></span>  
  
|<span data-ttu-id="04840-158">Valor</span><span class="sxs-lookup"><span data-stu-id="04840-158">Value</span></span>|<span data-ttu-id="04840-159">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="04840-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="04840-160">**Computador**</span><span class="sxs-lookup"><span data-stu-id="04840-160">**Computer**</span></span>|<span data-ttu-id="04840-161">O nome do computador no qual o evento de log ocorreu.</span><span class="sxs-lookup"><span data-stu-id="04840-161">The name of the computer on which the logged event occurred.</span></span>|  
|<span data-ttu-id="04840-162">**Operador**</span><span class="sxs-lookup"><span data-stu-id="04840-162">**Operator**</span></span>|<span data-ttu-id="04840-163">O nome de usuário da pessoa que iniciou o pacote.</span><span class="sxs-lookup"><span data-stu-id="04840-163">The user name of the person who started the package.</span></span>|  
|<span data-ttu-id="04840-164">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="04840-164">**SourceName**</span></span>|<span data-ttu-id="04840-165">O nome do pacote, contêiner ou tarefa no qual o evento de log ocorreu.</span><span class="sxs-lookup"><span data-stu-id="04840-165">The name of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="04840-166">**SourceID**</span><span class="sxs-lookup"><span data-stu-id="04840-166">**SourceID**</span></span>|<span data-ttu-id="04840-167">O Identificador Global Exclusivo (GUID) do pacote, contêiner ou tarefa no qual o evento de log ocorreu.</span><span class="sxs-lookup"><span data-stu-id="04840-167">The global unique identifier (GUID) of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="04840-168">**ExecutionID**</span><span class="sxs-lookup"><span data-stu-id="04840-168">**ExecutionID**</span></span>|<span data-ttu-id="04840-169">O Identificador Global Exclusivo da instância de execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="04840-169">The global unique identifier of the package execution instance.</span></span>|  
|<span data-ttu-id="04840-170">**MessageText**</span><span class="sxs-lookup"><span data-stu-id="04840-170">**MessageText**</span></span>|<span data-ttu-id="04840-171">Uma mensagem associada à entrada de log.</span><span class="sxs-lookup"><span data-stu-id="04840-171">A message associated with the log entry.</span></span>|  
|<span data-ttu-id="04840-172">**DataBytes**</span><span class="sxs-lookup"><span data-stu-id="04840-172">**DataBytes**</span></span>|<span data-ttu-id="04840-173">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="04840-173">Reserved for future use.</span></span>|  
  
 <span data-ttu-id="04840-174">**Basic**</span><span class="sxs-lookup"><span data-stu-id="04840-174">**Basic**</span></span>  
 <span data-ttu-id="04840-175">Marque ou desmarque os eventos para log.</span><span class="sxs-lookup"><span data-stu-id="04840-175">Select or clear events to log.</span></span> <span data-ttu-id="04840-176">Esta opção oculta os detalhes de log, exceto a lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="04840-176">This option hides logging details except the list of events.</span></span> <span data-ttu-id="04840-177">Se você selecionar um evento, por padrão, todos os detalhes de log serão selecionados para esse evento.</span><span class="sxs-lookup"><span data-stu-id="04840-177">If you select an event, all logging details are selected for the event by default.</span></span> <span data-ttu-id="04840-178">Clique em **Avançado** para mostrar todos os detalhes de log.</span><span class="sxs-lookup"><span data-stu-id="04840-178">Click **Advanced** to show all logging details.</span></span>  
  
 <span data-ttu-id="04840-179">**Carregar**</span><span class="sxs-lookup"><span data-stu-id="04840-179">**Load**</span></span>  
 <span data-ttu-id="04840-180">Especifique um arquivo XML existente para ser usado como modelo para definir as opções de log.</span><span class="sxs-lookup"><span data-stu-id="04840-180">Specify an existing XML file to use as a template for setting logging options.</span></span>  
  
 <span data-ttu-id="04840-181">**Salvar**</span><span class="sxs-lookup"><span data-stu-id="04840-181">**Save**</span></span>  
 <span data-ttu-id="04840-182">Salve os detalhes de configuração como um modelo para um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="04840-182">Save configuration details as a template to an XML file.</span></span>  
  
  
