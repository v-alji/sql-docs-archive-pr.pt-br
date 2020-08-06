---
title: Origem SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 749afb64-3567-4dc9-8431-783d650c25db
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d64af5e0d881e3b7dbbd2cc4e005aa3dbef3c43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582064"
---
# <a name="sap-bw-source"></a><span data-ttu-id="f1725-102">Origem SAP BW</span><span class="sxs-lookup"><span data-stu-id="f1725-102">SAP BW Source</span></span>
  <span data-ttu-id="f1725-103">A fonte SAP BW é o componente de fonte do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f1725-103">The SAP BW source is the source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="f1725-104">Assim, a origem do SAP BW extrai dados de um sistema SAP Netweaver BW versão 7 e torna estes dados disponíveis para o fluxo de dados em um pacote do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1725-104">Thus, the SAP BW source extracts data from an SAP Netweaver BW version 7 system and makes this data available to the data flow in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="f1725-105">Essa fonte tem uma saída e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="f1725-105">This source has one output and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f1725-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f1725-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="f1725-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="f1725-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f1725-108">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="f1725-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="f1725-109">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="f1725-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="f1725-110">Para usar a origem do SAP BW, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f1725-110">To use the SAP BW source, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="f1725-111">Prepare os objetos do SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="f1725-111">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="f1725-112">Conecte-se ao sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="f1725-112">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="f1725-113">Configure a origem do SAP BW</span><span class="sxs-lookup"><span data-stu-id="f1725-113">Configure the SAP BW source</span></span>](#bkmk_Configure_Source)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-source-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="f1725-114">Preparando os objetos do SAP Netweaver BW que a origem exige</span><span class="sxs-lookup"><span data-stu-id="f1725-114">Preparing the SAP Netweaver BW Objects That the Source Requires</span></span>  
 <span data-ttu-id="f1725-115">A origem do SAP BW exige que determinados objetos estejam no sistema SAP Netweaver BW antes que a origem possa funcionar.</span><span class="sxs-lookup"><span data-stu-id="f1725-115">The SAP BW source requires that certain objects are in the SAP Netweaver BW system before the source can function.</span></span> <span data-ttu-id="f1725-116">Se esses objetos ainda não existirem, siga estas etapas para criar e configurar esses objetos do sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f1725-116">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1725-117">Para obter detalhes adicionais sobre esses objetos e essas etapas de configuração, consulte a documentação do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f1725-117">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="f1725-118">Faça logon como SAP Netweaver BW com a GUI do SAP, digite o código de transação SM59 e crie um destino de RFC:</span><span class="sxs-lookup"><span data-stu-id="f1725-118">Log on to SAP Netweaver BW through the SAP GUI, enter transaction code SM59, and create an RFC destination:</span></span>  
  
    1.  <span data-ttu-id="f1725-119">Para **Tipo de conexão**, selecione **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="f1725-119">For **Connection Type**, select **TCP/IP**.</span></span>  
  
    2.  <span data-ttu-id="f1725-120">Para **Tipo de Ativação**, selecione **Programa de Servidor Registrado**.</span><span class="sxs-lookup"><span data-stu-id="f1725-120">For **Activation Type**, select **Registered Server Program**.</span></span>  
  
    3.  <span data-ttu-id="f1725-121">Para **Communication Type with Target System (Tipo de Comunicação com o Sistema de Destino)** , selecione **Non-Unicode (Inactive MDMP Settings) (Não Unicode (configurações de MDMP inativo))** .</span><span class="sxs-lookup"><span data-stu-id="f1725-121">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    4.  <span data-ttu-id="f1725-122">Atribuir uma ID de programa apropriada</span><span class="sxs-lookup"><span data-stu-id="f1725-122">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="f1725-123">Crie um destino do Open Hub:</span><span class="sxs-lookup"><span data-stu-id="f1725-123">Create an Open Hub Destination:</span></span>  
  
    1.  <span data-ttu-id="f1725-124">Vá para o Administrator Workbench (código de transação RSA1) e, no painel esquerdo, selecione **Destino do Open Hub**.</span><span class="sxs-lookup"><span data-stu-id="f1725-124">Go to the Administrator Workbench (transaction code RSA1) and, in the left pane, select **Open Hub Destination**.</span></span>  
  
    2.  <span data-ttu-id="f1725-125">No painel central, clique com o botão direito do mouse em uma InfoArea e selecione **“Criar o destino do Open Hub”** .</span><span class="sxs-lookup"><span data-stu-id="f1725-125">In the middle pane, right-click an InfoArea, and then select **"Create Open Hub Destination"**.</span></span>  
  
    3.  <span data-ttu-id="f1725-126">Para **Tipo de Destino**, selecione **“Ferramenta de Terceiros”** e insira o destino de RFC criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f1725-126">For **Destination Type**, select **"Third Party Tool"**, and then enter the previously created RFC Destination.</span></span>  
  
    4.  <span data-ttu-id="f1725-127">Salve e ative o novo destino do Open Hub.</span><span class="sxs-lookup"><span data-stu-id="f1725-127">Save and activate the new Open Hub Destination.</span></span>  
  
3.  <span data-ttu-id="f1725-128">Crie um processo de transferência de dados (DTP):</span><span class="sxs-lookup"><span data-stu-id="f1725-128">Create a Data Transfer Process (DTP):</span></span>  
  
    1.  <span data-ttu-id="f1725-129">No painel central da InfoArea, clique com o botão direito do mouse no destino criado anteriormente e selecione **“Criar o processo de transferência de dados”** .</span><span class="sxs-lookup"><span data-stu-id="f1725-129">In the middle pane of the InfoArea, right-click the previously created destination, and then select **"Create data transfer process"**.</span></span>  
  
    2.  <span data-ttu-id="f1725-130">Configurar, salvar e ativar o DTP.</span><span class="sxs-lookup"><span data-stu-id="f1725-130">Configure, save, and activate the DTP.</span></span>  
  
    3.  <span data-ttu-id="f1725-131">No menu, clique em **Ir para**e clique em **Configurações do Gerenciador de Lotes**.</span><span class="sxs-lookup"><span data-stu-id="f1725-131">On the menu, click **Goto**, and then click **Settings for Batch Manager**.</span></span>  
  
    4.  <span data-ttu-id="f1725-132">Atualizar **Número de Processos** para 1 para o processamento em série.</span><span class="sxs-lookup"><span data-stu-id="f1725-132">Update **Number of processes** to 1 for serial processing.</span></span>  
  
4.  <span data-ttu-id="f1725-133">Crie uma cadeia de processo:</span><span class="sxs-lookup"><span data-stu-id="f1725-133">Create a process chain:</span></span>  
  
    1.  <span data-ttu-id="f1725-134">Ao configurar a cadeia de processo, selecione **Iniciar usando a cadeia ou a API de metadados** como **Opções de Agendamento** de **Iniciar Processo**e adicione o DTP criado anteriormente como o nó subsequente.</span><span class="sxs-lookup"><span data-stu-id="f1725-134">When configuring the process chain, select the **Start Using Metadata Chain or API** as the **Scheduling Options** of the **Start Process**, and then add the previously created DTP as the subsequent node.</span></span>  
  
    2.  <span data-ttu-id="f1725-135">Salvar e ativar a cadeia do processo.</span><span class="sxs-lookup"><span data-stu-id="f1725-135">Save and activate the process chain.</span></span>  
  
     <span data-ttu-id="f1725-136">A origem do SAP BW pode chamar a cadeia de processo para ativar o processo de transferência de dados.</span><span class="sxs-lookup"><span data-stu-id="f1725-136">The SAP BW source can call the process chain to activate the data transfer process.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="f1725-137">Conectando-se ao sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="f1725-137">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="f1725-138">Para conectar-se ao sistema SAP Netweaver BW versão 7, a origem do SAP BW usará o gerenciador de conexões do SAP BW que faz parte do pacote do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f1725-138">To connect to the SAP Netweaver BW version 7 system, the SAP BW source uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="f1725-139">O gerenciador de conexões do SAP BW é o único gerenciador de conexões do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que a origem do SAP BW pode usar.</span><span class="sxs-lookup"><span data-stu-id="f1725-139">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW source can use.</span></span>  
  
 <span data-ttu-id="f1725-140">Para obter mais informações sobre o gerenciador de conexões do SAP BW, consulte [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f1725-140">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-source"></a><a name="bkmk_Configure_Source"></a> <span data-ttu-id="f1725-141">Configurando a origem do SAP BW</span><span class="sxs-lookup"><span data-stu-id="f1725-141">Configuring the SAP BW Source</span></span>  
 <span data-ttu-id="f1725-142">Você pode configurar a origem do SAP BW das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="f1725-142">You can configure the SAP BW source in the following ways:</span></span>  
  
-   <span data-ttu-id="f1725-143">Pesquise e selecione o destino do OHS (Open Hub Service) a ser usado para extrair dados.</span><span class="sxs-lookup"><span data-stu-id="f1725-143">Look up and select the Open Hub Service (OHS) destination to use to extract data.</span></span>  
  
-   <span data-ttu-id="f1725-144">Selecione um dos seguintes métodos para extrair dados:</span><span class="sxs-lookup"><span data-stu-id="f1725-144">Select one of the following methods for extracting data:</span></span>  
  
    -   <span data-ttu-id="f1725-145">Disparar uma cadeia de processo.</span><span class="sxs-lookup"><span data-stu-id="f1725-145">Trigger a process chain.</span></span> <span data-ttu-id="f1725-146">Nesse caso, o pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inicia o processo de extração.</span><span class="sxs-lookup"><span data-stu-id="f1725-146">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="f1725-147">Aguarde a notificação do sistema SAP Netweaver BW para iniciar uma extração.</span><span class="sxs-lookup"><span data-stu-id="f1725-147">Wait for notification from the SAP Netweaver BW system to begin an extraction.</span></span> <span data-ttu-id="f1725-148">Nesse caso, o sistema do SAP Netweaver BW inicia o processo de extração.</span><span class="sxs-lookup"><span data-stu-id="f1725-148">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="f1725-149">Recupere os dados associados a uma ID de solicitação específica</span><span class="sxs-lookup"><span data-stu-id="f1725-149">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="f1725-150">Nesse caso, o sistema SAP Netweaver BW já extraiu os dados para uma tabela interna e o pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] apenas lê os dados.</span><span class="sxs-lookup"><span data-stu-id="f1725-150">In this case, the SAP Netweaver BW system has already extracted the data to an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>  
  
-   <span data-ttu-id="f1725-151">Dependendo do método selecionado para extrair dados, forneça as seguintes informações adicionais:</span><span class="sxs-lookup"><span data-stu-id="f1725-151">Depending on the method selected for extracting data, provide the following additional information:</span></span>  
  
    -   <span data-ttu-id="f1725-152">Para a opção **P - Disparar Cadeia de Processo** , forneça o nome do host do gateway, o nome do serviço de gateway, a ID do programa para o destino do RFC e o nome da cadeia do processo.</span><span class="sxs-lookup"><span data-stu-id="f1725-152">For the **P - Trigger Process Chain** option, provide the gateway host name, gateway service name, program ID for the RFC destination, and name of the process chain.</span></span>  
  
    -   <span data-ttu-id="f1725-153">Para a opção **A - Aguardar Notificação** , forneça o nome do host do gateway, o nome do servidor do gateway e a ID do programa para o destino do RFC.</span><span class="sxs-lookup"><span data-stu-id="f1725-153">For the **W - Wait for Notify** option, provide the gateway host name, the gateway server name, and the program ID for the RFC destination.</span></span> <span data-ttu-id="f1725-154">Você também pode especificar o tempo limite (em segundos).</span><span class="sxs-lookup"><span data-stu-id="f1725-154">You can also specify the timeout (in seconds).</span></span> <span data-ttu-id="f1725-155">O tempo limite é o período de tempo máximo que a origem aguardará para ser notificada.</span><span class="sxs-lookup"><span data-stu-id="f1725-155">The timeout is the maximum period of time that the source will wait to be notified.</span></span>  
  
    -   <span data-ttu-id="f1725-156">Para a opção **E - Extrair Somente** , forneça a ID da solicitação.</span><span class="sxs-lookup"><span data-stu-id="f1725-156">For the **E - Extract Only** option, provide the Request ID.</span></span>  
  
-   <span data-ttu-id="f1725-157">Especifique as regras para conversão de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1725-157">Specify rules for string conversion.</span></span> <span data-ttu-id="f1725-158">(Por exemplo, converter todas as cadeias de caracteres dependendo se o sistema SAP Netweaver BW é Unicode ou não, ou converter todas as cadeias de caracteres para `varchar` ou `nvarchar`).</span><span class="sxs-lookup"><span data-stu-id="f1725-158">(For example, convert all strings depending on whether the SAP Netweaver BW system is Unicode or not, or convert all strings to `varchar` or `nvarchar`).</span></span>  
  
-   <span data-ttu-id="f1725-159">Use as opções que você selecionou para visualizar os dados que serão extraídos.</span><span class="sxs-lookup"><span data-stu-id="f1725-159">Use the options that you have selected to preview the data to be extracted.</span></span>  
  
 <span data-ttu-id="f1725-160">Você também pode habilitar o log das chamadas de função de RFC pela origem.</span><span class="sxs-lookup"><span data-stu-id="f1725-160">You can also enable logging of RFC function calls by the source.</span></span> <span data-ttu-id="f1725-161">(Esse log é separado do log opcional que você pode habilitar em pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Você habilita o log das chamadas de função de RFC quando configura o gerenciador de conexões do SAP BW que a origem usará.</span><span class="sxs-lookup"><span data-stu-id="f1725-161">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the source will use.</span></span> <span data-ttu-id="f1725-162">Para obter mais informações sobre como configurar o gerenciador de conexões do SAP BW, consulte [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f1725-162">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f1725-163">Se você não souber todos os valores necessários para configurar a origem, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="f1725-163">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="f1725-164">Para obter um passo a passo que demonstre como configurar e usar o gerenciador de conexões do SAP BW, a origem e o destino, consulte o white paper [Usando o SQL Server 2008 Integration Services com SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="f1725-164">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="f1725-165">Este white paper também mostra como configurar os objetos necessários no SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f1725-165">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="f1725-166">Usando o Designer SSIS para configurar a origem</span><span class="sxs-lookup"><span data-stu-id="f1725-166">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="f1725-167">Para obter mais informações sobre as propriedades da origem do SAP BW que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="f1725-167">For more information about the properties of the SAP BW source that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f1725-168">Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="f1725-168">SAP BW Source Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="f1725-169">Editor de Origem SAP BW &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="f1725-169">SAP BW Source Editor &#40;Columns Page&#41;</span></span>](sap-bw-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="f1725-170">Editor de Origem SAP BW &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="f1725-170">SAP BW Source Editor &#40;Error Output Page&#41;</span></span>](sap-bw-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="f1725-171">Editor de Origem SAP BW &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="f1725-171">SAP BW Source Editor &#40;Advanced Page&#41;</span></span>](sap-bw-source-editor-advanced-page.md)  
  
 <span data-ttu-id="f1725-172">Quando você estiver configurando a origem do SAP BW, também poderá usar várias caixas de diálogo para pesquisar objetos do SAP Netweaver BW ou visualizar os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="f1725-172">While you are configuring the SAP BW source, you can also use various dialog boxes to look up SAP Netweaver BW objects or to preview the source data.</span></span> <span data-ttu-id="f1725-173">Para obter mais informações sobre essas caixas de diálogo, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f1725-173">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f1725-174">Pesquisar destino RFC</span><span class="sxs-lookup"><span data-stu-id="f1725-174">Look Up RFC Destination</span></span>](look-up-rfc-destination.md)  
  
-   [<span data-ttu-id="f1725-175">Pesquisar cadeia de processo</span><span class="sxs-lookup"><span data-stu-id="f1725-175">Look Up Process Chain</span></span>](look-up-process-chain.md)  
  
-   [<span data-ttu-id="f1725-176">Log de solicitações</span><span class="sxs-lookup"><span data-stu-id="f1725-176">Request Log</span></span>](request-log.md)  
  
-   [<span data-ttu-id="f1725-177">Visualização</span><span class="sxs-lookup"><span data-stu-id="f1725-177">Preview</span></span>](preview.md)  
  
## <a name="see-also"></a><span data-ttu-id="f1725-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1725-178">See Also</span></span>  
 [<span data-ttu-id="f1725-179">Componentes do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="f1725-179">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
