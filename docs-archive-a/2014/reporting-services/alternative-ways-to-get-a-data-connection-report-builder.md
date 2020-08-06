---
title: Formas alternativas de obter uma conexão de dados (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aebc5f3d-97d5-4d54-b525-753fed073a9a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2be693469318172b2a55fbcb17b33e1deaaed3df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570547"
---
# <a name="alternative-ways-to-get-a-data-connection-report-builder"></a><span data-ttu-id="df07e-102">Formas alternativas de obter uma conexão de dados (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="df07e-102">Alternative Ways to Get a Data Connection (Report Builder)</span></span>
  <span data-ttu-id="df07e-103">Uma conexão de dados contém as informações para estabelecer conexões com uma fonte de dados externa, como um banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df07e-103">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="df07e-104">Geralmente, você obtém as informações sobre a conexão e o tipo de credenciais a ser usado do proprietário da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="df07e-104">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span>  
  
 <span data-ttu-id="df07e-105">Para especificar uma conexão de dados, é possível usar uma fonte de dados compartilhada do servidor de relatório ou criar uma fonte de dados inserida que será usada somente em um relatório específico.</span><span class="sxs-lookup"><span data-stu-id="df07e-105">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in a specific report.</span></span>  
  
 <span data-ttu-id="df07e-106">Na maioria dos tutoriais, você usa fontes de dados inseridas, mas se tiver acesso a fontes de dados compartilhadas, você poderá usá-las.</span><span class="sxs-lookup"><span data-stu-id="df07e-106">In most tutorials you use embedded data sources, but if you have access to shared data sources, then you can use them instead.</span></span>  
  
## <a name="getting-a-data-connection-from-a-shared-data-source"></a><span data-ttu-id="df07e-107">Obtendo uma conexão de dados de uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="df07e-107">Getting a Data Connection From a Shared Data Source</span></span>  
 <span data-ttu-id="df07e-108">Se o servidor de relatório tiver fontes de dados compartilhadas disponíveis que você possa usar, use-as em vez de uma fonte de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="df07e-108">If the report server has available shared data source that you have permissions to use, you can use them instead of an embedded data source.</span></span> <span data-ttu-id="df07e-109">Os procedimentos a seguir explicam como localizar as fontes de dados compartilhadas e como fornecer todas as credenciais necessárias para usá-las.</span><span class="sxs-lookup"><span data-stu-id="df07e-109">The following procedures tell how to locate the shared data sources and provide any credentials needed to use them.</span></span>  
  
 <span data-ttu-id="df07e-110">Para usar uma fonte de dados compartilhada, é necessário navegar até um servidor de relatório e selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="df07e-110">To use a shared data source, you must browse to a report server and select one.</span></span> <span data-ttu-id="df07e-111">Geralmente, você obtém o URL do servidor de relatório do administrador do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="df07e-111">Usually, you get the report server URL from the report server administrator.</span></span>  
  
#### <a name="to-specify-a-data-connection-from-a-list-of-shared-data-sources"></a><span data-ttu-id="df07e-112">Para especificar uma conexão de dados de uma lista de fontes de dados compartilhadas</span><span class="sxs-lookup"><span data-stu-id="df07e-112">To specify a data connection from a list of shared data sources</span></span>  
  
1.  <span data-ttu-id="df07e-113">Na página **Escolher um conjunto de dados** , selecione **Criar um conjunto de dados**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df07e-113">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="df07e-114">A página **Escolher uma conexão com uma fonte de dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="df07e-114">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="df07e-115">Na lista de fontes de dados, selecione uma que você tenha permissão para acessar.</span><span class="sxs-lookup"><span data-stu-id="df07e-115">From the list of data sources, select a data source that you have permission to access.</span></span>  
  
3.  <span data-ttu-id="df07e-116">Para verificar se é possível se conectar à fonte de dados, clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="df07e-116">To verify that you can connect to the data source, click **Test Connection**.</span></span> <span data-ttu-id="df07e-117">A mensagem "Conexão criada com êxito" será exibida.</span><span class="sxs-lookup"><span data-stu-id="df07e-117">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="df07e-118">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="df07e-118">Click **Next**.</span></span>  
  
     <span data-ttu-id="df07e-119">Se necessário, insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="df07e-119">If necessary, enter your credentials.</span></span> <span data-ttu-id="df07e-120">Para salvar as credenciais localmente, selecione **Salvar senha com a conexão**.</span><span class="sxs-lookup"><span data-stu-id="df07e-120">To save the credentials locally, select **Save password with connection**.</span></span> <span data-ttu-id="df07e-121">Se você não selecionar essa opção, deverá inserir credenciais sempre que executar o relatório</span><span class="sxs-lookup"><span data-stu-id="df07e-121">If you not select this option, you will be prompted for credentials every time that you run the report</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-specify-a-data-connection-by-browsing-to-a-shared-data-source-on-a-report-server"></a><span data-ttu-id="df07e-122">Para especificar uma conexão de dados navegando até uma fonte de dados compartilhada em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="df07e-122">To specify a data connection by browsing to a shared data source on a report server</span></span>  
  
1.  <span data-ttu-id="df07e-123">Na página **Escolher um conjunto de dados** , selecione **Criar um conjunto de dados**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df07e-123">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="df07e-124">A página **Escolher uma conexão com uma fonte de dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="df07e-124">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="df07e-125">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="df07e-125">Click **Browse**.</span></span> <span data-ttu-id="df07e-126">A caixa de diálogo **Selecionar Fonte de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="df07e-126">The **Select Data Source** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="df07e-127">Na lista suspensa **Examinar** , selecione **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="df07e-127">From the **Look in** drop-down list, select **Recent Sites and Servers**.</span></span> <span data-ttu-id="df07e-128">No painel da fonte de dados, clique na URL do servidor e em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="df07e-128">In the data source pane, click the URL for your server, and then click **Open**.</span></span>  
  
     <span data-ttu-id="df07e-129">A lista de fontes de dados ou modelos é exibida.</span><span class="sxs-lookup"><span data-stu-id="df07e-129">The list of data sources or models appears.</span></span>  
  
4.  <span data-ttu-id="df07e-130">Como alternativa, em **Nome**, digite a URL do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="df07e-130">Alternatively, in **Name**, type the URL to the report server.</span></span> <span data-ttu-id="df07e-131">Clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="df07e-131">Click **Open**.</span></span>  
  
     <span data-ttu-id="df07e-132">O Construtor de Relatórios é conectado ao servidor de relatório e carrega as fontes de dados disponíveis na pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="df07e-132">Report Builder connects to the report server and loads the data sources that are available at the root folder.</span></span>  
  
5.  <span data-ttu-id="df07e-133">Navegue até uma pasta que contém uma fonte de dados à qual você tenha permissões suficientes para se conectar, selecione-a e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="df07e-133">Navigate to a folder that contains a data source that you have sufficient permissions to connect to, select the data source, and then click **Open**.</span></span>  
  
     <span data-ttu-id="df07e-134">Você voltará à página **Escolher uma conexão com uma fonte de dados** .</span><span class="sxs-lookup"><span data-stu-id="df07e-134">You are back on the **Choose a connection to a data source** page.</span></span>  
  
6.  <span data-ttu-id="df07e-135">Para verificar se é possível se conectar à fonte de dados, clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="df07e-135">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="df07e-136">A mensagem "Conexão criada com êxito" será exibida.</span><span class="sxs-lookup"><span data-stu-id="df07e-136">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="df07e-137">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="df07e-137">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="df07e-138">Se for solicitado que você informe um nome de usuário e uma senha, insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="df07e-138">If you are prompted for a user name and password, enter your credentials.</span></span> <span data-ttu-id="df07e-139">Para salvar as credenciais localmente, selecione **Salvar senha com a conexão**.</span><span class="sxs-lookup"><span data-stu-id="df07e-139">To save the credentials locally, select **Save password with connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df07e-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df07e-140">See Also</span></span>  
 <span data-ttu-id="df07e-141">[Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="df07e-141">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="df07e-142">TUTORIAIS &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="df07e-142">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
