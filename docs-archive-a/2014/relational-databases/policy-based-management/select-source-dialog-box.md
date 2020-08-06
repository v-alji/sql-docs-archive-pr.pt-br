---
title: Caixa de diálogo Selecionar fonte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.selectsource.f1
ms.assetid: d664c2e5-dd0c-4da8-b27d-aa4ee4fc0ffd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 535d211d6827477fcf029accc27a9000e8c695c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685073"
---
# <a name="select-source-dialog-box"></a><span data-ttu-id="6fbb0-102">Caixa de diálogo Selecionar Origem</span><span class="sxs-lookup"><span data-stu-id="6fbb0-102">Select Source Dialog Box</span></span>
  <span data-ttu-id="6fbb0-103">Use esta caixa de diálogo para selecionar a origem das políticas a serem executadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-103">Use this dialog box to select the source of the policies to be run.</span></span> <span data-ttu-id="6fbb0-104">Para selecionar um ou mais arquivos XML que contêm políticas, selecione **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-104">To select one or more XML files that contain policies, select **Files**.</span></span> <span data-ttu-id="6fbb0-105">Para executar as políticas que são encontradas na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], selecione **Servidor**.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-105">To run the policies that are found on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select **Server**.</span></span>  
  
 <span data-ttu-id="6fbb0-106">Você pode abrir esta caixa de diálogo de vários modos.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-106">You can open this dialog box in several ways.</span></span>  
  
 <span data-ttu-id="6fbb0-107">**Para abrir essa caixa de diálogo**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-107">**To open this dialog box**</span></span>  
  
-   <span data-ttu-id="6fbb0-108">Em Servidores Registrados, clique com o botão direito do mouse em **Grupos do Servidor Local** ou em qualquer servidor em **Grupos de Servidores Locais**ou em **Servidores de Gerenciamento Central**e selecione **Avaliar Políticas**.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-108">In Registered Servers, right-click **Local Server Groups** or any server under **Local Server Groups**, or any server under **Central Management Servers**, and then select **Evaluate Policies**.</span></span> <span data-ttu-id="6fbb0-109">Na página **Seleção de Política** da caixa de diálogo **Avaliar Políticas** , clique no botão Procurar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="6fbb0-109">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="6fbb0-110">No Pesquisador de Objetos, expanda **Gerenciamento**, expanda **Gerenciamento de Políticas**, clique com o botão direito do mouse em **Políticas**e selecione **Importar Política**.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-110">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and select **Import Policy**.</span></span> <span data-ttu-id="6fbb0-111">Na caixa de diálogo **Importar** , clique no botão Procurar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="6fbb0-111">In the **Import** dialog box, click the Browse (**...**) button.</span></span>  
  
-   <span data-ttu-id="6fbb0-112">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor, banco de dados ou objeto de banco de dados, selecione **Políticas**e depois **Avaliar**.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-112">In Object Explorer, right-click a server, database, or database object, select **Policies**, and then select **Evaluate**.</span></span> <span data-ttu-id="6fbb0-113">Na página **Seleção de Política** da caixa de diálogo **Avaliar Políticas** , clique no botão Procurar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="6fbb0-113">In the **Policy Selection** page of the **Evaluate Policies** dialog box, click the Browse (**...**) button.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6fbb0-114">Opções</span><span class="sxs-lookup"><span data-stu-id="6fbb0-114">Options</span></span>  
 <span data-ttu-id="6fbb0-115">**Arquivos**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-115">**Files**</span></span>  
 <span data-ttu-id="6fbb0-116">Selecione um ou mais arquivos XML que contenham políticas.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-116">Select one or more XML files that contain policies.</span></span>  
  
 <span data-ttu-id="6fbb0-117">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-117">**Server**</span></span>  
 <span data-ttu-id="6fbb0-118">Permite que você selecione um servidor que contenha as políticas que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-118">Enables you to select a server that contains the policies that you want to run.</span></span>  
  
 <span data-ttu-id="6fbb0-119">**Tipo de servidor**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-119">**Server type**</span></span>  
 <span data-ttu-id="6fbb0-120">Só servidores [!INCLUDE[ssDE](../../includes/ssde-md.md)] contêm políticas.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-120">Only [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers contain policies.</span></span> <span data-ttu-id="6fbb0-121">Essa caixa é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-121">This box is read-only.</span></span>  
  
 <span data-ttu-id="6fbb0-122">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-122">**Server name**</span></span>  
 <span data-ttu-id="6fbb0-123">Selecione a instância do servidor com a qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-123">Select the server instance to connect to.</span></span> <span data-ttu-id="6fbb0-124">Por padrão, é exibida a instância do servidor usada na última conexão.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-124">By default, the server instance last connected to is displayed.</span></span>  
  
 <span data-ttu-id="6fbb0-125">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-125">**Authentication**</span></span>  
 <span data-ttu-id="6fbb0-126">Existem dois modos de autenticação disponíveis quando você se conecta com uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fbb0-126">Two authentication modes are available when you connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="6fbb0-127">**Modo de Autenticação do Windows (Autenticação do Windows)**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-127">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="6fbb0-128">O modo de Autenticação do Windows permite que um usuário se conecte por meio de uma conta de usuário Windows.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-128">Windows Authentication mode allows for a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="6fbb0-129">**Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-129">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="6fbb0-130">Quando um usuário se conecta com um nome de logon e senha especificados em uma conexão não confiável, o próprio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] efetua a autenticação, verificando se foi definida uma conta de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e se a senha especificada corresponde a uma senha registrada previamente.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-130">When a user connects with a specified login name and password from a nontrusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking whether a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and whether the specified password matches the one previously recorded.</span></span> <span data-ttu-id="6fbb0-131">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não tiver uma conta de logon definida, ocorrerá falha na autenticação e o usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-131">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6fbb0-132">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="6fbb0-133">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-133">**User name**</span></span>  
 <span data-ttu-id="6fbb0-134">Digite o nome do usuário com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-134">Enter the user name to connect with.</span></span> <span data-ttu-id="6fbb0-135">Essa opção só estará disponível se você tiver optado por conectar-se usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-135">This option is available only if you have selected to connect by using Windows Authentication.</span></span>  
  
 <span data-ttu-id="6fbb0-136">**Logon**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-136">**Login**</span></span>  
 <span data-ttu-id="6fbb0-137">Insira o logon com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-137">Enter the login to connect with.</span></span> <span data-ttu-id="6fbb0-138">Essa opção só estará disponível se você tiver optado por conectar-se usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fbb0-138">This option is available only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="6fbb0-139">**Senha**</span><span class="sxs-lookup"><span data-stu-id="6fbb0-139">**Password**</span></span>  
 <span data-ttu-id="6fbb0-140">Digite a senha do logon.</span><span class="sxs-lookup"><span data-stu-id="6fbb0-140">Enter the password for the login.</span></span> <span data-ttu-id="6fbb0-141">Essa opção poderá ser editada somente se você decidiu conectar-se usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fbb0-141">This option is editable only if you have selected to connect by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fbb0-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6fbb0-142">See Also</span></span>  
 <span data-ttu-id="6fbb0-143">[Nó de gerenciamento de política &#40;Pesquisador de Objetos&#41;](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="6fbb0-143">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="6fbb0-144">Administrar servidores com Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="6fbb0-144">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
