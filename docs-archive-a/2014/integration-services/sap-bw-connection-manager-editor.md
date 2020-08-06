---
title: SAP BW o editor do Gerenciador de conexões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ec970319-e749-4753-8675-9cf76ed99669
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 527af979fc9c92062f24e1fe161b93e88ed4ab4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680031"
---
# <a name="sap-bw-connection-manager-editor"></a><span data-ttu-id="62722-102">Editor do Gerenciador de Conexões de SAP BW</span><span class="sxs-lookup"><span data-stu-id="62722-102">SAP BW Connection Manager Editor</span></span>
  <span data-ttu-id="62722-103">Use **Editor do Gerenciador de Conexões do SAP BW** para especificar as propriedades a serem usadas para se conectar a um sistema SAP Netweaver BW versão 7.</span><span class="sxs-lookup"><span data-stu-id="62722-103">Use the **SAP BW Connection Manager Editor** to specify the properties to use to connect to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="62722-104">O gerenciador de conexões do SAP BW fornece conectividade para um sistema SAP Netweaver BW 7 para o uso pela origem ou destino do SAP BW.</span><span class="sxs-lookup"><span data-stu-id="62722-104">The SAP BW connection manager provides connectivity to an SAP Netweaver BW 7 system for use by the SAP BW source or destination.</span></span> <span data-ttu-id="62722-105">Para saber mais sobre o gerenciador de conexões do SAP BW do [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Gerenciador de conexões SAP BW](connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="62722-105">To learn more about the SAP BW connection manager of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Connection Manager](connection-manager/sap-bw-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="62722-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="62722-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="62722-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="62722-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="62722-108">**Para abrir o Gerenciador de Conexões do SAP BW**</span><span class="sxs-lookup"><span data-stu-id="62722-108">**To open the SAP BW Connection Manager Editor**</span></span>  
  
1.  <span data-ttu-id="62722-109">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o gerenciador de conexões do SAP BW.</span><span class="sxs-lookup"><span data-stu-id="62722-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that contains the SAP BW connection manager.</span></span>  
  
2.  <span data-ttu-id="62722-110">Na área Gerenciadores de Conexões na guia **Fluxo de Controle** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="62722-110">In the Connection Managers area on the **Control Flow** tab, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="62722-111">Clique duas vezes no gerenciador de conexões SAP BW.</span><span class="sxs-lookup"><span data-stu-id="62722-111">Double-click the SAP BW connection manager.</span></span>  
  
         <span data-ttu-id="62722-112">- ou -</span><span class="sxs-lookup"><span data-stu-id="62722-112">-or-</span></span>  
  
    -   <span data-ttu-id="62722-113">Clique com o botão direito do mouse no gerenciador de conexões SAP BW e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="62722-113">Right-click the SAP BW connection manager, and then select **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="62722-114">Opções</span><span class="sxs-lookup"><span data-stu-id="62722-114">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62722-115">Se você não souber todos os valores necessários para configurar o gerenciador de conexões, talvez precise perguntar ao administrador do SAP.</span><span class="sxs-lookup"><span data-stu-id="62722-115">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="62722-116">**Cliente**</span><span class="sxs-lookup"><span data-stu-id="62722-116">**Client**</span></span>  
 <span data-ttu-id="62722-117">Especifique o número de cliente do sistema.</span><span class="sxs-lookup"><span data-stu-id="62722-117">Specify the client number of the system.</span></span>  
  
 <span data-ttu-id="62722-118">**Idioma**</span><span class="sxs-lookup"><span data-stu-id="62722-118">**Language**</span></span>  
 <span data-ttu-id="62722-119">Especifique o idioma que o sistema usará.</span><span class="sxs-lookup"><span data-stu-id="62722-119">Specify the language that the system uses.</span></span> <span data-ttu-id="62722-120">Por exemplo, especifique **EN** para inglês.</span><span class="sxs-lookup"><span data-stu-id="62722-120">For example, specify **EN** for English.</span></span>  
  
 <span data-ttu-id="62722-121">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="62722-121">**User name**</span></span>  
 <span data-ttu-id="62722-122">Especifique o nome de usuário que será usado para conexão com o sistema.</span><span class="sxs-lookup"><span data-stu-id="62722-122">Specify the user name that will be used to connect to the system.</span></span>  
  
 <span data-ttu-id="62722-123">**Senha**</span><span class="sxs-lookup"><span data-stu-id="62722-123">**Password**</span></span>  
 <span data-ttu-id="62722-124">Especifique a senha que será usada com o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="62722-124">Specify the password that will be used with the user name.</span></span>  
  
 <span data-ttu-id="62722-125">**Usar servidor de aplicativo único**</span><span class="sxs-lookup"><span data-stu-id="62722-125">**Use single application server**</span></span>  
 <span data-ttu-id="62722-126">Conecte-se a um único servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="62722-126">Connect to a single application server.</span></span>  
  
 <span data-ttu-id="62722-127">Para se conectar a um grupo de servidores com balanceamento de carga, use a opção **Usar balanceamento de carga** .</span><span class="sxs-lookup"><span data-stu-id="62722-127">To connect to a group of load-balanced servers, use the **Use load balancing** option instead.</span></span>  
  
 <span data-ttu-id="62722-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="62722-128">**Host**</span></span>  
 <span data-ttu-id="62722-129">Se estiver se conectando a um único servidor de aplicativos, especifique o nome do host.</span><span class="sxs-lookup"><span data-stu-id="62722-129">If connecting to a single application server, specify the host name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62722-130">Esta opção só estará disponível se você tiver selecionado a opção **Usar servidor de aplicativo único** .</span><span class="sxs-lookup"><span data-stu-id="62722-130">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="62722-131">**Número do sistema**</span><span class="sxs-lookup"><span data-stu-id="62722-131">**System number**</span></span>  
 <span data-ttu-id="62722-132">Se estiver se conectando a um único servidor de aplicativos, especifique o número do sistema.</span><span class="sxs-lookup"><span data-stu-id="62722-132">If connecting to a single application server, specify the system number.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62722-133">Esta opção só estará disponível se você tiver selecionado a opção **Usar servidor de aplicativo único** .</span><span class="sxs-lookup"><span data-stu-id="62722-133">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="62722-134">**Usar balanceamento de carga**</span><span class="sxs-lookup"><span data-stu-id="62722-134">**Use load balancing**</span></span>  
 <span data-ttu-id="62722-135">Conecte-se a um grupo de servidores com balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="62722-135">Connect to a group of load-balanced servers.</span></span>  
  
 <span data-ttu-id="62722-136">Para conectar-se a um único servidor de aplicativos, use a opção **Usar servidor de aplicativo único** .</span><span class="sxs-lookup"><span data-stu-id="62722-136">To connect to a single application server, use the **Use single application server** option instead.</span></span>  
  
 <span data-ttu-id="62722-137">**Servidor de mensagens**</span><span class="sxs-lookup"><span data-stu-id="62722-137">**Message server**</span></span>  
 <span data-ttu-id="62722-138">Se estiver se conectando a um grupo de servidores com balanceamento de carga, especifique o nome do servidor de mensagens.</span><span class="sxs-lookup"><span data-stu-id="62722-138">If connecting to a group of load-balanced servers, specify the name of the message server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62722-139">Esta opção só estará disponível se você tiver selecionado a opção **Usar balanceamento de carga** .</span><span class="sxs-lookup"><span data-stu-id="62722-139">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="62722-140">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="62722-140">**Group**</span></span>  
 <span data-ttu-id="62722-141">Se estiver se conectando a um grupo de servidores com balanceamento de carga, especifique o nome do grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="62722-141">If connecting to a group of load-balanced servers, specify the name of the server group name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62722-142">Esta opção só estará disponível se você tiver selecionado a opção **Usar balanceamento de carga** .</span><span class="sxs-lookup"><span data-stu-id="62722-142">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="62722-143">**SIDs**</span><span class="sxs-lookup"><span data-stu-id="62722-143">**SID**</span></span>  
 <span data-ttu-id="62722-144">Se estiver se conectando a um grupo de servidores com balanceamento de carga, especifique a ID do sistema para a conexão.</span><span class="sxs-lookup"><span data-stu-id="62722-144">If connecting to a group of load-balanced servers, specify the System ID for the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62722-145">Esta opção só estará disponível se você tiver selecionado a opção **Usar balanceamento de carga** .</span><span class="sxs-lookup"><span data-stu-id="62722-145">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="62722-146">**Diretório de log**</span><span class="sxs-lookup"><span data-stu-id="62722-146">**Log directory**</span></span>  
 <span data-ttu-id="62722-147">Habilite o log para os componentes do [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 para SAP BW.</span><span class="sxs-lookup"><span data-stu-id="62722-147">Enable logging for the components of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 <span data-ttu-id="62722-148">Para habilitar o log, especifique um diretório para os arquivos de log que são criados antes e depois de cada chamada de função de RFC.</span><span class="sxs-lookup"><span data-stu-id="62722-148">To enable logging, specify a directory for the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="62722-149">(Esse recurso de registro cria muitos arquivos de log em formato XML.</span><span class="sxs-lookup"><span data-stu-id="62722-149">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="62722-150">Como esses arquivos de log também contêm todas as linhas de dados que são transferidas, esses arquivos de log podem consumir uma grande quantidade de espaço em disco.)</span><span class="sxs-lookup"><span data-stu-id="62722-150">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="62722-151">Se os dados que são transferidos contêm informações confidenciais, os arquivos de log também conterão essas informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="62722-151">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
 <span data-ttu-id="62722-152">Para especificar o diretório de log, você pode digitar o caminho de diretório manualmente ou clicar em **Procurar** e navegue até o diretório de log.</span><span class="sxs-lookup"><span data-stu-id="62722-152">To specify the log directory, you can either enter the directory path manually, or click **Browse** and browse to the log directory.</span></span>  
  
 <span data-ttu-id="62722-153">Se você não selecionar um diretório de log, o registro em log não será habilitado.</span><span class="sxs-lookup"><span data-stu-id="62722-153">If you do not select a log directory, logging is not enabled.</span></span>  
  
 <span data-ttu-id="62722-154">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="62722-154">**Browse**</span></span>  
 <span data-ttu-id="62722-155">Procurar para selecionar uma pasta para o diretório de log.</span><span class="sxs-lookup"><span data-stu-id="62722-155">Browse to select a folder for the log directory.</span></span>  
  
 <span data-ttu-id="62722-156">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="62722-156">**Test Connection**</span></span>  
 <span data-ttu-id="62722-157">Teste a conexão usando os valores que você forneceu.</span><span class="sxs-lookup"><span data-stu-id="62722-157">Test the connection using the values that you have provided.</span></span> <span data-ttu-id="62722-158">Depois de clicar em **Testar Conexão**, uma caixa de mensagem aparecerá e indicará se a conexão foi bem-sucedida ou falhou.</span><span class="sxs-lookup"><span data-stu-id="62722-158">After clicking **Test Connection**, a message box appears and indicates whether the connection succeeded or failed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62722-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62722-159">See Also</span></span>  
 [<span data-ttu-id="62722-160">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="62722-160">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
  
  
