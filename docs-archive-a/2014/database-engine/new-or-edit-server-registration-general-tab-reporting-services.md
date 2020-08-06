---
title: Novo ou editar registro de servidor (guia geral) (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.reportserver.f1
ms.assetid: 5f899a8e-52ef-46b5-b7a9-f200ccd9f724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 195756498dcefe4686d4b06e758dba9919c0b304
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582608"
---
# <a name="new-or-edit-server-registration-general-tab-reporting-services"></a><span data-ttu-id="33f54-102">Novo registro ou editar registro de servidor (guia Geral) (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="33f54-102">New or Edit Server Registration (General Tab) (Reporting Services)</span></span>
  <span data-ttu-id="33f54-103">Use essa guia para especificar opções ao registrar uma instância do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33f54-103">Use this tab to specify options when registering an instance of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="33f54-104">Para acessar essa página, em Servidores Registrados, clique em **Reporting Services** na barra de ferramentas **Servidores Registrados** , clique com o botão direito do mouse em qualquer grupo de servidores registrados, como **Reporting Services**, aponte para **Novo**e clique em **Registro de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="33f54-104">To access this page, in Registered Servers, click **Reporting Services** on the **Registered Servers** toolbar, right-click any registered servers group such as **Reporting Services**, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="33f54-105">Opções</span><span class="sxs-lookup"><span data-stu-id="33f54-105">Options</span></span>  
 <span data-ttu-id="33f54-106">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="33f54-106">**Server type**</span></span>  
 <span data-ttu-id="33f54-107">Quando um servidor é registrado a partir de servidores registrados, a caixa **tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido no painel **servidores registrados** .</span><span class="sxs-lookup"><span data-stu-id="33f54-107">When a server is registered from Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in the **Registered Servers** pane.</span></span> <span data-ttu-id="33f54-108">Para registrar um tipo de servidor diferente, clique no servidor desejado na barra de ferramentas **Servidores Registrados** antes de começar a registrar um novo servidor.</span><span class="sxs-lookup"><span data-stu-id="33f54-108">To register a different type of server, click the server you want on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="33f54-109">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="33f54-109">**Server name**</span></span>  
 <span data-ttu-id="33f54-110">Especifique a instância do servidor de relatório para se conectar.</span><span class="sxs-lookup"><span data-stu-id="33f54-110">Specify the report server instance to connect to.</span></span> <span data-ttu-id="33f54-111">No [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], você pode acessar um servidor de relatório por meio de seu nome de instância.</span><span class="sxs-lookup"><span data-stu-id="33f54-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], you can access a report server through its instance name.</span></span> <span data-ttu-id="33f54-112">Você pode ter uma instância de servidor de relatório para cada instância de SQL Server que instala.</span><span class="sxs-lookup"><span data-stu-id="33f54-112">You can have one report server instance for each SQL Server instance that you install.</span></span> <span data-ttu-id="33f54-113">Se você estiver usando a instância padrão, digite o nome da instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33f54-113">If you are using the default instance, type the name of the SQL Server instance.</span></span> <span data-ttu-id="33f54-114">Caso esteja usando uma instância nomeada, especifique a instância nomeada para se conectar ao servidor de relatório no formato MSSQL$InstanceName.</span><span class="sxs-lookup"><span data-stu-id="33f54-114">If you are using a named instance, specify the named instance to connect to the report server in the format MSSQL$InstanceName.</span></span>  
  
 <span data-ttu-id="33f54-115">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="33f54-115">**Authentication**</span></span>  
 <span data-ttu-id="33f54-116">A autenticação para um servidor de relatório é feita pelo Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="33f54-116">Authentication to a report server is made through Internet Information Services (IIS).</span></span> <span data-ttu-id="33f54-117">Selecione um dos seguintes modos de autenticação ao se conectar ao Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="33f54-117">Select from one of the following authentication modes when connecting to Reporting Services:</span></span>  
  
 <span data-ttu-id="33f54-118">**Modo de Autenticação do Windows (Autenticação do Windows)**</span><span class="sxs-lookup"><span data-stu-id="33f54-118">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="33f54-119">Conecte-se à instância de servidor de relatório usando as credenciais do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="33f54-119">Connect to the report server instance using your [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials.</span></span>  
  
 <span data-ttu-id="33f54-120">**Autenticação básica**</span><span class="sxs-lookup"><span data-stu-id="33f54-120">**Basic Authentication**</span></span>  
 <span data-ttu-id="33f54-121">Conecte-se usando a **Autenticação Básica** se a instalação do Reporting Services estiver configurada para usar a Autenticação Básica.</span><span class="sxs-lookup"><span data-stu-id="33f54-121">Connect using **Basic Authentication** if your Reporting Services installation is configured to use Basic Authentication.</span></span>  
  
 <span data-ttu-id="33f54-122">**Autenticação de Formulários**</span><span class="sxs-lookup"><span data-stu-id="33f54-122">**Forms Authentication**</span></span>  
 <span data-ttu-id="33f54-123">Conecte-se usando a **Autenticação de Formulários** se a instalação do Reporting Services estiver configurada para usar uma extensão de autenticação personalizada.</span><span class="sxs-lookup"><span data-stu-id="33f54-123">Connect using **Forms Authentication** if your Reporting Services installation is configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="33f54-124">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="33f54-124">**User Name**</span></span>  
 <span data-ttu-id="33f54-125">Digite o nome de logon a ser usado na conexão.</span><span class="sxs-lookup"><span data-stu-id="33f54-125">Enter the login name to use for the connection.</span></span> <span data-ttu-id="33f54-126">Essa opção estará disponível somente se você selecionou **Básica** ou **Autenticação de Formulários**.</span><span class="sxs-lookup"><span data-stu-id="33f54-126">This option is only available if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="33f54-127">**Senha**</span><span class="sxs-lookup"><span data-stu-id="33f54-127">**Password**</span></span>  
 <span data-ttu-id="33f54-128">Digite a senha para o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="33f54-128">Enter the password for the user name.</span></span> <span data-ttu-id="33f54-129">Essa opção só poderá ser editada se você selecionou **Básica** ou **Autenticação de Formulários**.</span><span class="sxs-lookup"><span data-stu-id="33f54-129">This option is only editable if you have selected **Basic** or **Forms Authentication**.</span></span>  
  
 <span data-ttu-id="33f54-130">**Lembrar senha**</span><span class="sxs-lookup"><span data-stu-id="33f54-130">**Remember password**</span></span>  
 <span data-ttu-id="33f54-131">Armazene a senha que você digitou.</span><span class="sxs-lookup"><span data-stu-id="33f54-131">Store the password you have entered.</span></span> <span data-ttu-id="33f54-132">Essa opção só estará disponível se você clicou em **Básico** ou **Autenticação de Formatos**.</span><span class="sxs-lookup"><span data-stu-id="33f54-132">This option is only available if you have clicked **Basic** or **Forms Authentication**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33f54-133"> Caso tenha armazenado a senha e não deseja mais fazê-lo, desmarque essa caixa de seleção e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33f54-133">If you have stored the password and want to stop storing it, clear this check box and then click **Save**.</span></span>  
  
 <span data-ttu-id="33f54-134">**Nome do servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="33f54-134">**Registered server name**</span></span>  
 <span data-ttu-id="33f54-135">O nome que você deseja exibir em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="33f54-135">The name you want to appear in Registered Servers.</span></span> <span data-ttu-id="33f54-136">Esse nome não precisa corresponder ao nome na caixa **Nome do servidor** .</span><span class="sxs-lookup"><span data-stu-id="33f54-136">This name does not have to match the name in the **Server name** box.</span></span>  
  
 <span data-ttu-id="33f54-137">**Descrição do servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="33f54-137">**Registered server description**</span></span>  
 <span data-ttu-id="33f54-138">Digite uma descrição opcional do servidor.</span><span class="sxs-lookup"><span data-stu-id="33f54-138">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="33f54-139">**Test**</span><span class="sxs-lookup"><span data-stu-id="33f54-139">**Test**</span></span>  
 <span data-ttu-id="33f54-140">Clique para testar a conexão com o servidor selecionado em **Nome do servidor**.</span><span class="sxs-lookup"><span data-stu-id="33f54-140">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="33f54-141">**Salvar**</span><span class="sxs-lookup"><span data-stu-id="33f54-141">**Save**</span></span>  
 <span data-ttu-id="33f54-142">Clique para salvar as configurações do servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="33f54-142">Click to save the registered server settings.</span></span>  
  
  
