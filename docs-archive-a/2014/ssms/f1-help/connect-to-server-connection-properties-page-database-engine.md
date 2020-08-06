---
title: Conectar ao Mecanismo de Banco de Dados do Servidor (página Propriedades da Conexão) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttosqlserver.connectionproperties.f1
ms.assetid: edc1143c-6a47-4b02-92ab-441bdea8ea8a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 41f2aa3fd5004a371515ee5d8905c7bb73699829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684431"
---
# <a name="connect-to-server-connection-properties-page-database-engine"></a><span data-ttu-id="d5d71-102">Conectar ao Servidor (página Propriedades da Conexão) Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="d5d71-102">Connect to Server (Connection Properties Page) Database Engine</span></span>
  <span data-ttu-id="d5d71-103">Use esta guia para exibir ou especificar opções ao se conectar a uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ou registrar [!INCLUDE[ssDE](../../includes/ssde-md.md)] em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="d5d71-103">Use this tab to view or specify options when connecting to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or registering [!INCLUDE[ssDE](../../includes/ssde-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="d5d71-104">**Conectar** e **Opções** só são exibidas nesta caixa de diálogo ao conectar-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5d71-104">**Connect** and **Options** only appear in this dialog box when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="d5d71-105">**Testar** e **Salvar** só aparecem nesta caixa de diálogo durante o registro no [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5d71-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5d71-106">Opções</span><span class="sxs-lookup"><span data-stu-id="d5d71-106">Options</span></span>  
 <span data-ttu-id="d5d71-107">**Conectar ao banco de dados**</span><span class="sxs-lookup"><span data-stu-id="d5d71-107">**Connect to database**</span></span>  
 <span data-ttu-id="d5d71-108">Selecione um banco de dados com o qual deseja se conectar na lista.</span><span class="sxs-lookup"><span data-stu-id="d5d71-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="d5d71-109">Se você selecionar **\<default>** , você será conectado ao banco de dados padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="d5d71-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="d5d71-110">Se você selecionar **\<Browse server>** , poderá procurar no servidor o banco de dados ao qual deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="d5d71-110">If you select **\<Browse server>**, you can browse the server for the database to which to connect.</span></span>  
  
 <span data-ttu-id="d5d71-111">Ao conectar-se a uma instância do Mecanismo de Banco de Dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], você deve usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e especificar um banco de dados na caixa de diálogo **Conectar ao Servidor** , na guia **Propriedades da Conexão** . Verifique se você marcou a caixa de seleção **Criptografar conexão** .</span><span class="sxs-lookup"><span data-stu-id="d5d71-111">When connecting to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine through [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], you must use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication and specify a database in the **Connect to Server** dialog box, on the **Connection Properties** tab. Ensure that you select the **Encrypt connection** checkbox.</span></span>  
  
 <span data-ttu-id="d5d71-112">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conecta-se ao **mestre**.</span><span class="sxs-lookup"><span data-stu-id="d5d71-112">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to **master**.</span></span> <span data-ttu-id="d5d71-113">Se você especificar um banco de dados de usuário, consultará somente esse banco de dados e seus objetos no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="d5d71-113">If you specify a user database, you will only see that database and its objects in Object Explorer.</span></span> <span data-ttu-id="d5d71-114">Se você se conectar ao **mestre**, poderá ver todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d5d71-114">If you connect to **master**, you will be able to see all databases.</span></span> <span data-ttu-id="d5d71-115">Para obter mais informações, consulte [visão geral do banco de dados SQL do Azure](/azure/sql-database/sql-database-technical-overview).</span><span class="sxs-lookup"><span data-stu-id="d5d71-115">For more information, see the [Azure SQL Database Overview](/azure/sql-database/sql-database-technical-overview).</span></span>  
  
 <span data-ttu-id="d5d71-116">**Protocolo de rede**</span><span class="sxs-lookup"><span data-stu-id="d5d71-116">**Network protocol**</span></span>  
 <span data-ttu-id="d5d71-117">Selecione um protocolo na lista.</span><span class="sxs-lookup"><span data-stu-id="d5d71-117">Select a protocol from the list.</span></span> <span data-ttu-id="d5d71-118">Os protocolos cliente disponíveis são aqueles que você configurou usando a Configuração de Rede Cliente no Gerenciamento do Computador.</span><span class="sxs-lookup"><span data-stu-id="d5d71-118">The available client protocols are those that you configured using the Client Network Configuration in Computer Management.</span></span>  
  
 <span data-ttu-id="d5d71-119">**Tamanho do pacote de rede**</span><span class="sxs-lookup"><span data-stu-id="d5d71-119">**Network packet size**</span></span>  
 <span data-ttu-id="d5d71-120">Digite o tamanho dos pacotes de rede a serem enviados.</span><span class="sxs-lookup"><span data-stu-id="d5d71-120">Enter the size of the network packets to be sent.</span></span> <span data-ttu-id="d5d71-121">O padrão é 4096 bytes.</span><span class="sxs-lookup"><span data-stu-id="d5d71-121">The default is 4096 bytes.</span></span>  
  
 <span data-ttu-id="d5d71-122">**Tempo limite da conexão**</span><span class="sxs-lookup"><span data-stu-id="d5d71-122">**Connection timeout**</span></span>  
 <span data-ttu-id="d5d71-123">Insira o número de segundos de espera para que uma conexão seja estabelecida antes de atingir o tempo limite. O valor padrão é 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="d5d71-123">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="d5d71-124">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="d5d71-124">**Execution timeout**</span></span>  
 <span data-ttu-id="d5d71-125">Digite o tempo em segundos que se deve esperar antes que a execução de uma tarefa seja concluída no servidor.</span><span class="sxs-lookup"><span data-stu-id="d5d71-125">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="d5d71-126">O valor padrão é zero segundo, o que indica que não há nenhum tempo limite.</span><span class="sxs-lookup"><span data-stu-id="d5d71-126">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="d5d71-127">**Criptografar a conexão**</span><span class="sxs-lookup"><span data-stu-id="d5d71-127">**Encrypt connection**</span></span>  
 <span data-ttu-id="d5d71-128">Força a criptografia da conexão.</span><span class="sxs-lookup"><span data-stu-id="d5d71-128">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="d5d71-129">**Usar cor personalizada**</span><span class="sxs-lookup"><span data-stu-id="d5d71-129">**Use custom color**</span></span>  
 <span data-ttu-id="d5d71-130">Selecione para especificar a cor do plano de fundo para a barra de status em uma janela do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5d71-130">Select to specify the background color for the status bar in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="d5d71-131">Para especificar a cor, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="d5d71-131">To specify the color, click **Select**.</span></span> <span data-ttu-id="d5d71-132">Na caixa de diálogo **Cor** , selecione uma cor predefinida na grade **Cores básicas** ou clique em **Definir cores personalizadas** para definir e usar uma cor personalizada.</span><span class="sxs-lookup"><span data-stu-id="d5d71-132">In the **Color** dialog box, select a predefined color from the **Basic Colors** grid or click **Define Custom Colors** to define and use a custom color.</span></span>  
  
-   <span data-ttu-id="d5d71-133">Quando você especifica uma cor para uma entrada de servidor no painel **Pesquisador de Objetos** , aquela cor é usada quando você abre uma janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="d5d71-133">When you specify a color for a server entry in the **Object Explorer** pane, that color is used when you open a Query Editor window.</span></span> <span data-ttu-id="d5d71-134">Para abrir uma janela do Editor de Consultas, clique com o botão direito do mouse em entrada de servidor e selecione **Nova Consulta**ou, quando o painel **Pesquisador de Objetos** estiver ativo e focalizado neste servidor, clique em **Nova Consulta** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="d5d71-134">To open a Query Editor window, either right-click the server entry and select **New Query**; or, when the **Object Explorer** pane is active and focused on this server, click **New Query** on the toolbar.</span></span>  
  
-   <span data-ttu-id="d5d71-135">Quando você especifica uma cor para uma entrada de servidor no painel **Servidores Registrados** , aquela cor é usada quando você abre uma janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="d5d71-135">When you specify a color for a server entry in the **Registered Servers** pane, that color is used when you open a Query Editor window.</span></span> <span data-ttu-id="d5d71-136">Para abrir uma janela do Editor de Consultas, clique com o botão direito do mouse em entrada de servidor e selecione **Nova Consulta**ou, quando o painel **Servidor Registrado** estiver ativo e focalizado neste servidor, clique em **Nova Consulta** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="d5d71-136">To open a Query Editor window, either right-click the server entry and select **New Query**; or, when the **Registered Server** pane is active and focused on this server, click **New Query** on the toolbar.</span></span>  
  
-   <span data-ttu-id="d5d71-137">No menu **Arquivo** , quando você clica em **Novo** e depois em **Consulta do Mecanismo do Banco de Dados**, a cor que você especifica na caixa de diálogo **Conectar ao Servidor** aplica-se àquela janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="d5d71-137">On the **File** menu, when you click **New** and then **Database Engine Query**, the color you that you specify in the **Connect to Server** dialog box applies to that Query Editor window.</span></span>  
  
 <span data-ttu-id="d5d71-138">**Redefinir Tudo**</span><span class="sxs-lookup"><span data-stu-id="d5d71-138">**Reset All**</span></span>  
 <span data-ttu-id="d5d71-139">Substitua todos os valores de propriedade de conexão digitados manualmente por seus padrões.</span><span class="sxs-lookup"><span data-stu-id="d5d71-139">Replace all manually entered connection property values with their defaults.</span></span>  
  
 <span data-ttu-id="d5d71-140">**Connect**</span><span class="sxs-lookup"><span data-stu-id="d5d71-140">**Connect**</span></span>  
 <span data-ttu-id="d5d71-141">Tenta estabelecer uma conexão usando os valores listados.</span><span class="sxs-lookup"><span data-stu-id="d5d71-141">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="d5d71-142">**Opções**</span><span class="sxs-lookup"><span data-stu-id="d5d71-142">**Options**</span></span>  
 <span data-ttu-id="d5d71-143">Clique para alterar a caixa de diálogo e ocultar as opções de conexão de servidor adicionais, como lembrar a senha.</span><span class="sxs-lookup"><span data-stu-id="d5d71-143">Click to change the dialog box and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="d5d71-144">**Test**</span><span class="sxs-lookup"><span data-stu-id="d5d71-144">**Test**</span></span>  
 <span data-ttu-id="d5d71-145">Ao registrar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] em **Servidores Registrados**, clique para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d5d71-145">When registering [!INCLUDE[ssDE](../../includes/ssde-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="d5d71-146">**Salvar**</span><span class="sxs-lookup"><span data-stu-id="d5d71-146">**Save**</span></span>  
 <span data-ttu-id="d5d71-147">Salve as configurações em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="d5d71-147">Saves the settings in **Registered Servers**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d71-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5d71-148">See Also</span></span>  
 [<span data-ttu-id="d5d71-149">caixa de diálogo Propriedades da conexão</span><span class="sxs-lookup"><span data-stu-id="d5d71-149">Connection Properties Dialog Box</span></span>](../../database-engine/connection-properties-dialog-box.md)  
  
  
