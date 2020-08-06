---
title: Conectar ao Servidor (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectoserverunknownservertype.f1
- sql12.swb.connection.login.sqlserver.f1
- sql12.swb.connection.login.sqlce.f1
- sql12.swb.manageSS2k.f1
- sql12.swb.connecttoce.f1
- sql12.swb.connecttoce.connectionproperties.f1
ms.assetid: ee9017b4-8a19-4360-9003-9e6484082d41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca227d1a3bbc13160962ba2fcad23ff011c950f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681356"
---
# <a name="connect-to-server-database-engine"></a><span data-ttu-id="bed58-102">Conectar ao Servidor (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="bed58-102">Connect to Server (Database Engine)</span></span>
  <span data-ttu-id="bed58-103">Use essa caixa de diálogo para exibir ou especificar opções ao se conectar ao [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed58-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="bed58-104">Na maioria das vezes, é possível conectar-se informando o nome do computador do servidor de banco de dados na caixa **Nome do servidor** e clicando em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bed58-104">In most cases, you can connect by entering the computer name of the database server in the **Server name** box and then clicking **Connect**.</span></span> <span data-ttu-id="bed58-105">Se você estiver se conectando ao [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use o nome do computador seguido por **\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="bed58-105">If you are connecting to [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use the computer name followed by **\sqlexpress**.</span></span>  
  
 <span data-ttu-id="bed58-106">Muitos fatores podem afetar sua possibilidade de conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed58-106">Many factors can affect your ability to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="bed58-107">Opções</span><span class="sxs-lookup"><span data-stu-id="bed58-107">Options</span></span>  
 <span data-ttu-id="bed58-108">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="bed58-108">**Server type**</span></span>  
 <span data-ttu-id="bed58-109">Ao registrar um servidor a partir do Pesquisador de Objetos, selecione o tipo de servidor ao qual se conectar: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]ou [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed58-109">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="bed58-110">O restante da caixa de diálogo mostra somente as opções que válidas ao tipo de servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="bed58-110">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="bed58-111">Ao registrar um servidor de Servidores Registrados, a caixa **Tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido no componente Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="bed58-111">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="bed58-112">Para registrar um tipo diferente de servidor, selecione [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)]ou [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] na barra de ferramentas Servidores Registrados antes de começar a registrar um novo servidor.</span><span class="sxs-lookup"><span data-stu-id="bed58-112">To register a different type of server, select [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="bed58-113">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="bed58-113">**Server name**</span></span>  
 <span data-ttu-id="bed58-114">Selecione a instância do servidor com a qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="bed58-114">Select the server instance to connect to.</span></span> <span data-ttu-id="bed58-115">Por padrão, é exibida a instância de servidor usada na última conexão.</span><span class="sxs-lookup"><span data-stu-id="bed58-115">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bed58-116">Para se conectar a uma instância de usuário ativa do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , conecte-se usando o protocolo de pipes nomeados especificando o nome do pipe, por exemplo, np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query. Para obter mais informações, consulte a documentação do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bed58-116">To connect to an active user instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] connect using named pipes protocol specifying the pipe name, such as np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query For more information, see the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="bed58-117">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="bed58-117">**Authentication**</span></span>  
 <span data-ttu-id="bed58-118">Existem dois modos de autenticação disponíveis quando se estabelece conexão com uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed58-118">Two authentication modes are available when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="bed58-119">**Modo de Autenticação do Windows (Autenticação do Windows)**</span><span class="sxs-lookup"><span data-stu-id="bed58-119">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="bed58-120">O modo de Autenticação do Windows permite que um usuário se conecte por uma conta de usuário Windows.</span><span class="sxs-lookup"><span data-stu-id="bed58-120">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="bed58-121">**Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bed58-121">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="bed58-122">Quando um usuário se conecta com um nome de logon e uma senha especificados em uma conexão não confiável, o próprio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] efetua a autenticação verificando se foi definida uma conta de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e se a senha especificada corresponde a uma senha já registrada.</span><span class="sxs-lookup"><span data-stu-id="bed58-122">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="bed58-123">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não tiver uma conta de logon definida, ocorrerá falha na autenticação e o usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="bed58-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bed58-124">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="bed58-124">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="bed58-125">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="bed58-125">**User name**</span></span>  
 <span data-ttu-id="bed58-126">Digite o nome do usuário com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="bed58-126">Enter the user name to connect with.</span></span> <span data-ttu-id="bed58-127">Essa opção estará disponível somente se você decidiu conectar-se usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="bed58-127">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="bed58-128">**Logon**</span><span class="sxs-lookup"><span data-stu-id="bed58-128">**Login**</span></span>  
 <span data-ttu-id="bed58-129">Insira o logon com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="bed58-129">Enter the login to connect with.</span></span> <span data-ttu-id="bed58-130">Essa opção estará disponível somente se você decidiu conectar-se usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bed58-130">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="bed58-131">**Senha**</span><span class="sxs-lookup"><span data-stu-id="bed58-131">**Password**</span></span>  
 <span data-ttu-id="bed58-132">Digite a senha do logon.</span><span class="sxs-lookup"><span data-stu-id="bed58-132">Enter the password for the login.</span></span> <span data-ttu-id="bed58-133">Essa opção poderá ser editada somente se você decidiu conectar-se usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bed58-133">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="bed58-134">**Connect**</span><span class="sxs-lookup"><span data-stu-id="bed58-134">**Connect**</span></span>  
 <span data-ttu-id="bed58-135">Clique para conectar-se com o servidor selecionado acima.</span><span class="sxs-lookup"><span data-stu-id="bed58-135">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="bed58-136">**Opções**</span><span class="sxs-lookup"><span data-stu-id="bed58-136">**Options**</span></span>  
 <span data-ttu-id="bed58-137">Clique para exibir opções de conexão de servidor adicionais, como registrar um servidor e lembrar a senha.</span><span class="sxs-lookup"><span data-stu-id="bed58-137">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
