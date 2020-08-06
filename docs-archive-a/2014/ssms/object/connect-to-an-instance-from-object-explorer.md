---
title: Conectar a uma instância do Pesquisador de Objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9803a8a0-a8f1-4b65-87b8-989b06850194
author: stevestein
ms.author: sstein
ms.openlocfilehash: 918dd3ed6e8eb765f2cb7077107407c324c51a4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568328"
---
# <a name="connect-to-an-instance-from-object-explorer"></a><span data-ttu-id="aa240-102">Conectar-se a uma instância do Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="aa240-102">Connect to an Instance From Object Explorer</span></span>
  <span data-ttu-id="aa240-103">Para gerenciar objetos usando o Pesquisador de Objetos, primeiro você deve conectar o Pesquisador de Objetos à instância que contém os objetos.</span><span class="sxs-lookup"><span data-stu-id="aa240-103">To manage objects by using Object Explorer, you must first connect Object Explorer to the instance that contains the objects.</span></span> <span data-ttu-id="aa240-104">Você pode conectar o Pesquisador de Objetos a várias instâncias ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="aa240-104">You can connect Object Explorer to multiple instances at the same time.</span></span>  
  
## <a name="connecting-object-explorer-to-a-server"></a><span data-ttu-id="aa240-105">Conectando o Pesquisador de Objetos a um servidor</span><span class="sxs-lookup"><span data-stu-id="aa240-105">Connecting Object Explorer to a Server</span></span>  
 <span data-ttu-id="aa240-106">Para usar o Pesquisador de Objetos, você deve primeiro se conectar a um servidor.</span><span class="sxs-lookup"><span data-stu-id="aa240-106">To use Object Explorer you must first connect to a server.</span></span> <span data-ttu-id="aa240-107">Clique em **Conectar** na barra de ferramentas do Pesquisador de Objetos e escolha o tipo de servidor na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="aa240-107">Click **Connect** on the Object Explorer toolbar and choose the type of server from the drop-down list.</span></span> <span data-ttu-id="aa240-108">A caixa de diálogo **Conectar ao Servidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="aa240-108">The **Connect to Server** dialog box opens.</span></span> <span data-ttu-id="aa240-109">Para se conectar, você deve fornecer pelo menos o nome do servidor e as informações de autenticação corretas.</span><span class="sxs-lookup"><span data-stu-id="aa240-109">To connect, you must provide at least the name of the server and the correct authentication information.</span></span>  
  
## <a name="optional-object-explorer-connection-settings"></a><span data-ttu-id="aa240-110">Configurações de conexão opcional do Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="aa240-110">Optional Object Explorer Connection Settings</span></span>  
 <span data-ttu-id="aa240-111">Ao se conectar a um servidor, você pode especificar informações adicionais de conexão na caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="aa240-111">When connecting to a server, you can specify additional connection information in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="aa240-112">A caixa de diálogo **Conectar ao Servidor** reterá as últimas configurações usadas e conexões novas, como novas janelas do editor de códigos, e usará essas configurações.</span><span class="sxs-lookup"><span data-stu-id="aa240-112">The **Connect to Server** dialog box will retain the last used settings, and new connections, such as new code editor windows, will use those settings.</span></span>  
  
 <span data-ttu-id="aa240-113">Para especificar configurações de conexão opcionais, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="aa240-113">To specify optional connection settings, follow these steps:</span></span>  
  
1.  <span data-ttu-id="aa240-114">Clique em **Conectar** na barra de ferramentas do Pesquisador de Objetos e clique no tipo de servidor para fazer a conexão.</span><span class="sxs-lookup"><span data-stu-id="aa240-114">Click **Connect** on the Object Explorer toolbar, and click the type of server to connect to.</span></span> <span data-ttu-id="aa240-115">A caixa de diálogo **Conectar-se ao Servidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="aa240-115">The **Connect to Server** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="aa240-116">Na caixa **Nome do Servidor** , digite o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa240-116">In the **Server Name** box, type the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
3.  <span data-ttu-id="aa240-117">Clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="aa240-117">Click **Options**.</span></span> <span data-ttu-id="aa240-118">A caixa de diálogo **Conectar ao Servidor** exibe opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="aa240-118">The **Connect to Server** dialog box displays additional options.</span></span>  
  
4.  <span data-ttu-id="aa240-119">Clique na guia **Propriedades da Conexão** para definir as configurações adicionais.</span><span class="sxs-lookup"><span data-stu-id="aa240-119">Click the **Connection Properties** tab to configure the additional settings.</span></span> <span data-ttu-id="aa240-120">As configurações disponíveis variam, dependendo do tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="aa240-120">The settings that are available vary depending upon the server type.</span></span> <span data-ttu-id="aa240-121">As configurações a seguir estão disponíveis para o [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa240-121">The following settings are available for the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
    |<span data-ttu-id="aa240-122">Configuração</span><span class="sxs-lookup"><span data-stu-id="aa240-122">Setting</span></span>|<span data-ttu-id="aa240-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="aa240-123">Description</span></span>|  
    |-------------|-----------------|  
    |<span data-ttu-id="aa240-124">**Conectar ao banco de dados**</span><span class="sxs-lookup"><span data-stu-id="aa240-124">**Connect to database**</span></span>|<span data-ttu-id="aa240-125">Escolha um dos bancos de dados disponíveis no servidor.</span><span class="sxs-lookup"><span data-stu-id="aa240-125">Choose from the available databases on the server.</span></span> <span data-ttu-id="aa240-126">Esta lista só mostrará bancos de dados que você tem permissão para exibição.</span><span class="sxs-lookup"><span data-stu-id="aa240-126">This list will only show databases that you have permission to view.</span></span>|  
    |<span data-ttu-id="aa240-127">**Protocolo de rede**</span><span class="sxs-lookup"><span data-stu-id="aa240-127">**Network protocol**</span></span>|<span data-ttu-id="aa240-128">Selecione entre Memória Compartilhada, TCP/IP ou Pipes Nomeados.</span><span class="sxs-lookup"><span data-stu-id="aa240-128">Select from Shared Memory, TCP/IP, or Named Pipes.</span></span>|  
    |<span data-ttu-id="aa240-129">**Tamanho do pacote de rede**</span><span class="sxs-lookup"><span data-stu-id="aa240-129">**Network packet size**</span></span>|<span data-ttu-id="aa240-130">Configurar em bytes.</span><span class="sxs-lookup"><span data-stu-id="aa240-130">Configure in bytes.</span></span> <span data-ttu-id="aa240-131">A configuração padrão é 4096 bytes.</span><span class="sxs-lookup"><span data-stu-id="aa240-131">The default setting is 4096 bytes.</span></span>|  
    |<span data-ttu-id="aa240-132">**Tempo limite da conexão**</span><span class="sxs-lookup"><span data-stu-id="aa240-132">**Connection timeout**</span></span>|<span data-ttu-id="aa240-133">Configurar em segundos.</span><span class="sxs-lookup"><span data-stu-id="aa240-133">Configure in seconds.</span></span> <span data-ttu-id="aa240-134">A configuração padrão é 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="aa240-134">The default setting is 15 seconds.</span></span>|  
    |<span data-ttu-id="aa240-135">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="aa240-135">**Execution timeout**</span></span>|<span data-ttu-id="aa240-136">Configurar em segundos.</span><span class="sxs-lookup"><span data-stu-id="aa240-136">Configure in seconds.</span></span> <span data-ttu-id="aa240-137">A configuração padrão (0) indica que a execução nunca vai expirar.</span><span class="sxs-lookup"><span data-stu-id="aa240-137">The default setting (0) indicates that execution will never time out.</span></span>|  
    |<span data-ttu-id="aa240-138">**Criptografar a conexão**</span><span class="sxs-lookup"><span data-stu-id="aa240-138">**Encrypt connection**</span></span>|<span data-ttu-id="aa240-139">Força a criptografia.</span><span class="sxs-lookup"><span data-stu-id="aa240-139">Forces encryption.</span></span>|  
  
5.  <span data-ttu-id="aa240-140">Para adicionar o servidor especificado a sua lista de servidores registrados, clique na guia **Servidor Registrado** , clique no local em que você deseja exibir o servidor novo e conclua a conexão.</span><span class="sxs-lookup"><span data-stu-id="aa240-140">To add the specified server to your list of registered servers, click the **Registered Server** tab, click on the location where you want the new server to appear, and then complete the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa240-141">Use a página **Parâmetros Adicionais de Conexão** para acrescentar mais parâmetros de conexão à cadeia de conexões.</span><span class="sxs-lookup"><span data-stu-id="aa240-141">Use the **Additional Connection Parameters** page to add more connection parameters to the connection string.</span></span> <span data-ttu-id="aa240-142">Para obter mais informações, consulte [Conectar ao servidor &#40;página Parâmetros de Conexão Adicionais& 41;](../../database-engine/connect-to-server-additional-connection-parameters-page.md).</span><span class="sxs-lookup"><span data-stu-id="aa240-142">For more information, see [Connect to Server &#40;Additional Connection Parameters Page&#41;](../../database-engine/connect-to-server-additional-connection-parameters-page.md).</span></span>  
  
  