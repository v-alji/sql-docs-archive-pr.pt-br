---
title: Editor de Origem SAP BW (página Gerenciador de Conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2a6dc531-85ca-43c5-a65f-3ad3f7d537c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c6b1782daf8c00b3b3d3a7d13b5ffa00adeeba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678885"
---
# <a name="sap-bw-source-editor-connection-manager-page"></a><span data-ttu-id="a4c93-102">Editor de Origem SAP BW (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="a4c93-102">SAP BW Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="a4c93-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem SAP BW** para selecionar o gerenciador de conexões SAP BW para a origem de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a4c93-103">Use the **Connection Manager** page of the **SAP BW Source Editor** to select the SAP BW connection manager for the SAP BW source.</span></span> <span data-ttu-id="a4c93-104">Nesta página, você também seleciona o modo de execução e os parâmetros para extrair os dados do sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a4c93-104">On this page, you also select the execution mode and the parameters for extracting the data from the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="a4c93-105">Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="a4c93-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a4c93-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a4c93-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a4c93-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="a4c93-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a4c93-108">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="a4c93-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="a4c93-109">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="a4c93-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="a4c93-110">**Para abrir a página Gerenciador de Conexões**</span><span class="sxs-lookup"><span data-stu-id="a4c93-110">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="a4c93-111">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a4c93-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="a4c93-112">Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a4c93-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="a4c93-113">No **Editor de Origem SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="a4c93-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="a4c93-114">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="a4c93-114">Static Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4c93-115">Se você não souber todos os valores necessários para configurar a origem, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="a4c93-115">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a4c93-116">**Gerenciador de conexões SAP BW**</span><span class="sxs-lookup"><span data-stu-id="a4c93-116">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="a4c93-117">Selecione um gerenciador de conexões existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="a4c93-117">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a4c93-118">**Novo**</span><span class="sxs-lookup"><span data-stu-id="a4c93-118">**New**</span></span>  
 <span data-ttu-id="a4c93-119">Crie um novo gerenciador de conexões, usando a caixa de diálogo **Gerenciador de Conexões SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="a4c93-119">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a4c93-120">Para obter mais informações sobre essa caixa de diálogo, consulte [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a4c93-120">For more information about this dialog box, see [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="a4c93-121">**Destino OHS**</span><span class="sxs-lookup"><span data-stu-id="a4c93-121">**OHS destination**</span></span>  
 <span data-ttu-id="a4c93-122">Selecione o destino do OHS (Open Hub Service) a ser usado para extrair dados da origem.</span><span class="sxs-lookup"><span data-stu-id="a4c93-122">Select the Open Hub Service (OHS) destination to use to extract data from the source.</span></span>  
  
 <span data-ttu-id="a4c93-123">**Modo de execução**</span><span class="sxs-lookup"><span data-stu-id="a4c93-123">**Execution mode**</span></span>  
 <span data-ttu-id="a4c93-124">Especifique o método para extrair os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="a4c93-124">Specify the method for extracting data from the source.</span></span>  
  
|<span data-ttu-id="a4c93-125">Opção</span><span class="sxs-lookup"><span data-stu-id="a4c93-125">Option</span></span>|<span data-ttu-id="a4c93-126">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a4c93-126">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a4c93-127">**P - Disparar Cadeia de Processo**</span><span class="sxs-lookup"><span data-stu-id="a4c93-127">**P - Trigger Process Chain**</span></span>|<span data-ttu-id="a4c93-128">Disparar uma cadeia de processo.</span><span class="sxs-lookup"><span data-stu-id="a4c93-128">Trigger a process chain.</span></span> <span data-ttu-id="a4c93-129">Nesse caso, o pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inicia o processo de extração.</span><span class="sxs-lookup"><span data-stu-id="a4c93-129">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>|  
|<span data-ttu-id="a4c93-130">**A - Aguardar Notificação**</span><span class="sxs-lookup"><span data-stu-id="a4c93-130">**W - Wait for Notify**</span></span>|<span data-ttu-id="a4c93-131">Aguarde a notificação do sistema SAP Netweaver BW para iniciar a extração dos dados.</span><span class="sxs-lookup"><span data-stu-id="a4c93-131">Wait for notification from the SAP Netweaver BW system to begin extracting the data.</span></span> <span data-ttu-id="a4c93-132">Nesse caso, o sistema do SAP Netweaver BW inicia o processo de extração.</span><span class="sxs-lookup"><span data-stu-id="a4c93-132">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>|  
|<span data-ttu-id="a4c93-133">**E - Extrair Somente**</span><span class="sxs-lookup"><span data-stu-id="a4c93-133">**E - Extract Only**</span></span>|<span data-ttu-id="a4c93-134">Recupere os dados associados a uma ID de solicitação específica</span><span class="sxs-lookup"><span data-stu-id="a4c93-134">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="a4c93-135">Nesse caso, o sistema SAP Netweaver BW já extraiu os dados em uma tabela interna e o pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] apenas lê os dados.</span><span class="sxs-lookup"><span data-stu-id="a4c93-135">In this case, the SAP Netweaver BW system has already extracted the data into an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>|  
  
 <span data-ttu-id="a4c93-136">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="a4c93-136">**Preview**</span></span>  
 <span data-ttu-id="a4c93-137">Abra a caixa de diálogo **Visualizar** em que você pode visualizar os resultados.</span><span class="sxs-lookup"><span data-stu-id="a4c93-137">Open the **Preview** dialog box in which you can preview results.</span></span> <span data-ttu-id="a4c93-138">Para obter mais informações, consulte [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="a4c93-138">For more information, see [Preview](preview.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a4c93-139">A opção **Visualizar** , que está disponível na página **Gerenciador de Conexões** do editor de origem SAP BW, extrai dados de fato.</span><span class="sxs-lookup"><span data-stu-id="a4c93-139">The **Preview** option, that is available on the **Connection Manager** page of the SAP BW Source Editor, actually extracts data.</span></span> <span data-ttu-id="a4c93-140">Se você configurou o SAP Netweaver BW para extrair apenas os dados que foram alterados desde a extração anterior, selecionar **Visualizar** excluirá os dados visualizados da próxima extração.</span><span class="sxs-lookup"><span data-stu-id="a4c93-140">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="a4c93-141">Quando você clica em **Visualizar**, também abre a caixa de diálogo **Log de Solicitações** .</span><span class="sxs-lookup"><span data-stu-id="a4c93-141">When you click **Preview**, you also open the **Request Log** dialog box.</span></span> <span data-ttu-id="a4c93-142">Você pode usar essa caixa de diálogo para exibir os eventos que são registrados em log durante a solicitação que é feita no sistema SAP Netweaver BW para dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="a4c93-142">You can use this dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="a4c93-143">Para obter mais informações, consulte [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="a4c93-143">For more information, see [Request Log](request-log.md).</span></span>  
  
## <a name="execution-mode-dynamic-options"></a><span data-ttu-id="a4c93-144">Opções dinâmicas do modo de execução</span><span class="sxs-lookup"><span data-stu-id="a4c93-144">Execution Mode Dynamic Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4c93-145">Se você não souber todos os valores necessários para configurar a origem, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="a4c93-145">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
### <a name="execution-mode--p---trigger-process-chain"></a><span data-ttu-id="a4c93-146">Modo de execução = P - Disparar Cadeia de Processo</span><span class="sxs-lookup"><span data-stu-id="a4c93-146">Execution Mode = P - Trigger Process Chain</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="a4c93-147">Opções de destino RFC</span><span class="sxs-lookup"><span data-stu-id="a4c93-147">RFC Destination Options</span></span>  
 <span data-ttu-id="a4c93-148">Você não precisa saber e inserir esses valores com antecedência.</span><span class="sxs-lookup"><span data-stu-id="a4c93-148">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="a4c93-149">Use o botão **Pesquisar** para localizar e selecionar o destino RFC apropriado.</span><span class="sxs-lookup"><span data-stu-id="a4c93-149">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="a4c93-150">Depois de selecionar um destino RFC, o componente insere os valores apropriados para essas opções.</span><span class="sxs-lookup"><span data-stu-id="a4c93-150">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="a4c93-151">**Host do gateway**</span><span class="sxs-lookup"><span data-stu-id="a4c93-151">**Gateway host**</span></span>  
 <span data-ttu-id="a4c93-152">Digite o nome do servidor ou endereço IP do host do gateway.</span><span class="sxs-lookup"><span data-stu-id="a4c93-152">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="a4c93-153">Em geral, o nome ou o endereço IP é o mesmo que o servidor de aplicativos do SAP.</span><span class="sxs-lookup"><span data-stu-id="a4c93-153">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="a4c93-154">**Serviço do gateway**</span><span class="sxs-lookup"><span data-stu-id="a4c93-154">**Gateway service**</span></span>  
 <span data-ttu-id="a4c93-155">Digite o nome do serviço de gateway, no formato `sapgwNN`, em que `NN` é o número do sistema.</span><span class="sxs-lookup"><span data-stu-id="a4c93-155">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="a4c93-156">**ID do Programa**</span><span class="sxs-lookup"><span data-stu-id="a4c93-156">**Program ID**</span></span>  
 <span data-ttu-id="a4c93-157">Insira a ID do programa que está associada ao destino RFC.</span><span class="sxs-lookup"><span data-stu-id="a4c93-157">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="a4c93-158">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="a4c93-158">**Look up**</span></span>  
 <span data-ttu-id="a4c93-159">Pesquisar o destino RFC usando a caixa de diálogo **Pesquisar Destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="a4c93-159">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="a4c93-160">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a4c93-160">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
#### <a name="process-chain-options"></a><span data-ttu-id="a4c93-161">Opções da cadeia do processo</span><span class="sxs-lookup"><span data-stu-id="a4c93-161">Process Chain Options</span></span>  
 <span data-ttu-id="a4c93-162">Você não precisa saber e inserir esses valores com antecedência.</span><span class="sxs-lookup"><span data-stu-id="a4c93-162">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="a4c93-163">Use o botão **Pesquisar** para localizar e selecionar a cadeia de processo apropriada.</span><span class="sxs-lookup"><span data-stu-id="a4c93-163">Use the **Look up** button to find and select the appropriate process chain.</span></span> <span data-ttu-id="a4c93-164">Depois de selecionar uma cadeia de processo, o componente insere o valor apropriado para a opção.</span><span class="sxs-lookup"><span data-stu-id="a4c93-164">After you select a process chain, the component enters the appropriate value for the option.</span></span>  
  
 <span data-ttu-id="a4c93-165">**Cadeia de processo**</span><span class="sxs-lookup"><span data-stu-id="a4c93-165">**Process chain**</span></span>  
 <span data-ttu-id="a4c93-166">Digite o nome da cadeia de processo a ser disparada pela origem.</span><span class="sxs-lookup"><span data-stu-id="a4c93-166">Enter the name of the process chain to be triggered by the source.</span></span>  
  
 <span data-ttu-id="a4c93-167">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="a4c93-167">**Look up**</span></span>  
 <span data-ttu-id="a4c93-168">Pesquisar a cadeia de processo usando a caixa de diálogo **Pesquisar Cadeia de Processo** .</span><span class="sxs-lookup"><span data-stu-id="a4c93-168">Look up the process chain by using the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="a4c93-169">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up Process Chain](look-up-process-chain.md).</span><span class="sxs-lookup"><span data-stu-id="a4c93-169">For more information about this dialog box, see [Look Up Process Chain](look-up-process-chain.md).</span></span>  
  
### <a name="execution-mode--w---wait-for-notify"></a><span data-ttu-id="a4c93-170">Modo de execução = A - Aguardar Notificação</span><span class="sxs-lookup"><span data-stu-id="a4c93-170">Execution Mode = W - Wait for Notify</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="a4c93-171">Opções de destino RFC</span><span class="sxs-lookup"><span data-stu-id="a4c93-171">RFC Destination Options</span></span>  
 <span data-ttu-id="a4c93-172">Você não precisa saber e inserir esses valores com antecedência.</span><span class="sxs-lookup"><span data-stu-id="a4c93-172">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="a4c93-173">Use o botão **Pesquisar** para localizar e selecionar o destino RFC apropriado.</span><span class="sxs-lookup"><span data-stu-id="a4c93-173">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="a4c93-174">Depois de selecionar um destino RFC, o componente insere os valores apropriados para as opções.</span><span class="sxs-lookup"><span data-stu-id="a4c93-174">After you select an RFC destination, the component enters the appropriate values for the options.</span></span>  
  
 <span data-ttu-id="a4c93-175">**Host do gateway**</span><span class="sxs-lookup"><span data-stu-id="a4c93-175">**Gateway host**</span></span>  
 <span data-ttu-id="a4c93-176">Digite o nome do servidor ou endereço IP do host do gateway.</span><span class="sxs-lookup"><span data-stu-id="a4c93-176">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="a4c93-177">Em geral, o nome ou o endereço IP é o mesmo que o servidor de aplicativos do SAP.</span><span class="sxs-lookup"><span data-stu-id="a4c93-177">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="a4c93-178">**Serviço do gateway**</span><span class="sxs-lookup"><span data-stu-id="a4c93-178">**Gateway service**</span></span>  
 <span data-ttu-id="a4c93-179">Digite o nome do serviço de gateway, no formato `sapgwNN`, em que `NN` é o número do sistema.</span><span class="sxs-lookup"><span data-stu-id="a4c93-179">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="a4c93-180">**ID do Programa**</span><span class="sxs-lookup"><span data-stu-id="a4c93-180">**Program ID**</span></span>  
 <span data-ttu-id="a4c93-181">Insira a ID do programa que está associada ao destino RFC.</span><span class="sxs-lookup"><span data-stu-id="a4c93-181">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="a4c93-182">**Pesquisar**</span><span class="sxs-lookup"><span data-stu-id="a4c93-182">**Look up**</span></span>  
 <span data-ttu-id="a4c93-183">Pesquisar o destino RFC usando a caixa de diálogo **Pesquisar Destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="a4c93-183">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="a4c93-184">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a4c93-184">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="execution-mode--e---extract-only"></a><span data-ttu-id="a4c93-185">Modo de execução = E - Extrair Somente</span><span class="sxs-lookup"><span data-stu-id="a4c93-185">Execution Mode = E - Extract Only</span></span>  
 <span data-ttu-id="a4c93-186">**Request ID**</span><span class="sxs-lookup"><span data-stu-id="a4c93-186">**Request ID**</span></span>  
 <span data-ttu-id="a4c93-187">Insira a ID de solicitação que está associada à extração.</span><span class="sxs-lookup"><span data-stu-id="a4c93-187">Enter the Request ID that is associated with the extraction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c93-188">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4c93-188">See Also</span></span>  
 <span data-ttu-id="a4c93-189">[Editor de Origem SAP BW &#40;Página Colunas&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a4c93-189">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="a4c93-190">[Editor de Origem SAP BW &#40;Página Saída de Erro&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a4c93-190">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="a4c93-191">[Editor de Origem SAP BW &#40;Página Avançado&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="a4c93-191">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="a4c93-192">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a4c93-192">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
