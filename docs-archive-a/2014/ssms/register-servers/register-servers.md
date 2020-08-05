---
title: Registrar servidores
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlserverregisteredserver.dhelp
helpviewer_keywords:
- connections [SQL Server], registered servers
- registering servers
- servers [SQL Server], registering
- server management [SQL Server], registering servers
- server registration [SQL Server]
ms.assetid: c2a2513e-fa09-419c-99e7-a12d57c5a0db
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f4b23ba127c6b000b0abbe832c4c072ada78c5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572316"
---
# <a name="register-servers"></a><span data-ttu-id="6f425-102">Registrar servidores</span><span class="sxs-lookup"><span data-stu-id="6f425-102">Register Servers</span></span>
  <span data-ttu-id="6f425-103">O registro de um servidor no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lhe permite armazenar as informações de conexão de servidor para conexões futuras. Há três modos de registrar um servidor no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f425-103">Registering a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] allows you to store the server connection information for future connections.There are three ways to register a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="6f425-104">As instâncias locais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são registradas automaticamente durante a primeira inicialização do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] após sua instalação.</span><span class="sxs-lookup"><span data-stu-id="6f425-104">Local instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are automatically registered during the first launch of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] after its installation.</span></span>  
  
2.  <span data-ttu-id="6f425-105">Você também pode iniciar a qualquer hora o processo de registro automático, para restaurar o registro de instâncias do servidor local.</span><span class="sxs-lookup"><span data-stu-id="6f425-105">You can also initiate the automatic registration process at any time, to restore the registration of local server instances.</span></span>  
  
3.  <span data-ttu-id="6f425-106">E ainda, você pode registrar um servidor usando a ferramenta Servidores Registrados no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f425-106">Lastly, you can register a server using the Registered Servers tool in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="benefits-of-registered-servers"></a><span data-ttu-id="6f425-107">Benefícios dos Servidores Registrados</span><span class="sxs-lookup"><span data-stu-id="6f425-107">Benefits of Registered Servers</span></span>  
 <span data-ttu-id="6f425-108">Com os Servidores Registrados, você pode:</span><span class="sxs-lookup"><span data-stu-id="6f425-108">With Registered Servers you can:</span></span>  
  
-   <span data-ttu-id="6f425-109">Registrar servidores para preservar as informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="6f425-109">Register servers to preserve the connection information.</span></span>  
  
-   <span data-ttu-id="6f425-110">Determinar se um servidor registrado está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="6f425-110">Determine if a registered server is running.</span></span>  
  
-   <span data-ttu-id="6f425-111">Conectar facilmente o Pesquisador de Objetos e o Editor de Consultas a um servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="6f425-111">Easily connect Object Explorer and Query Editor to a registered server.</span></span>  
  
-   <span data-ttu-id="6f425-112">Editar ou excluir as informações de registro de um servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="6f425-112">Edit or delete the registration information for a registered server.</span></span>  
  
-   <span data-ttu-id="6f425-113">Criar grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="6f425-113">Create groups of servers.</span></span>  
  
-   <span data-ttu-id="6f425-114">Fornecer nomes amigáveis para servidores registrados fornecendo um valor na caixa **Nome do servidor registrado** , que é diferente da lista **Nome do servidor** .</span><span class="sxs-lookup"><span data-stu-id="6f425-114">Provide user-friendly names for registered servers by providing a value in the **Registered server name** box that is different from the **Server name** list.</span></span>  
  
-   <span data-ttu-id="6f425-115">Fornecer descrições detalhadas dos servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="6f425-115">Provide detailed descriptions for registered servers.</span></span>  
  
-   <span data-ttu-id="6f425-116">Fornecer descrições detalhadas dos grupos de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="6f425-116">Provide detailed descriptions of registered server groups.</span></span>  
  
-   <span data-ttu-id="6f425-117">Exportar grupos de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="6f425-117">Export registered server groups.</span></span>  
  
-   <span data-ttu-id="6f425-118">Importar grupos de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="6f425-118">Import registered server groups.</span></span>  
  
-   <span data-ttu-id="6f425-119">Exibir os arquivos de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para instâncias online ou offline do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f425-119">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files for online or offline instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6f425-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6f425-120">Related Tasks</span></span>  
 <span data-ttu-id="6f425-121">Use os seguintes tópicos como introdução rápida a servidores registrados:</span><span class="sxs-lookup"><span data-stu-id="6f425-121">Use the following topics to get started with registered servers:</span></span>  
  
|<span data-ttu-id="6f425-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6f425-122">**Description**</span></span>|<span data-ttu-id="6f425-123">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="6f425-123">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="6f425-124">Registrar instâncias do servidor local</span><span class="sxs-lookup"><span data-stu-id="6f425-124">Register local server instances</span></span>|[<span data-ttu-id="6f425-125">Registrar um servidor conectado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-125">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](register-a-connected-server-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-126">Registrar um servidor</span><span class="sxs-lookup"><span data-stu-id="6f425-126">Register a server</span></span>|[<span data-ttu-id="6f425-127">Criar um novo servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-127">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-128">Exibir servidores registrados</span><span class="sxs-lookup"><span data-stu-id="6f425-128">View registered servers</span></span>|[<span data-ttu-id="6f425-129">Exibir Servidores Registrados no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f425-129">View Registered Servers in SQL Server Management Studio</span></span>](view-registered-servers-in-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-130">Remover um servidor registrado</span><span class="sxs-lookup"><span data-stu-id="6f425-130">Remove a registered server</span></span>|[<span data-ttu-id="6f425-131">Remover um servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-131">Remove a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](remove-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-132">Alterar um registro de servidor</span><span class="sxs-lookup"><span data-stu-id="6f425-132">Change a server's registration</span></span>|[<span data-ttu-id="6f425-133">Alterar um registro do servidor &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-133">Change a Server's Registration &#40;SQL Server Management Studio&#41;</span></span>](change-a-server-s-registration-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-134">Conectar-se com um servidor registrado</span><span class="sxs-lookup"><span data-stu-id="6f425-134">Connect to a registered server</span></span>|[<span data-ttu-id="6f425-135">Conectar-se a um servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-135">Connect to a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](connect-to-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-136">Desconectar de um servidor registrado</span><span class="sxs-lookup"><span data-stu-id="6f425-136">Disconnect from a registered server</span></span>|[<span data-ttu-id="6f425-137">Desconectar-se de um Servidor Registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-137">Disconnect from a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](disconnect-from-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-138">Mover um servidor registrado ou grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6f425-138">Move a registered server or server group</span></span>|[<span data-ttu-id="6f425-139">Mover um servidor registrado ou um grupo de Servidores Registrados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-139">Move a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](move-a-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="6f425-140">Altere o nome de um servidor registrado ou grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6f425-140">Change the name of a registered server or server group</span></span>|[<span data-ttu-id="6f425-141">Alterar o nome de um Servidor Registrado ou de um grupo de Servidores Registrados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-141">Change the Name of a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](change-the-name-of-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="6f425-142">Criar ou editar um grupo de servidor</span><span class="sxs-lookup"><span data-stu-id="6f425-142">Create or edit a server group</span></span>|[<span data-ttu-id="6f425-143">Criar ou editar um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-143">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-or-edit-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-144">Remover um grupo de servidor</span><span class="sxs-lookup"><span data-stu-id="6f425-144">Remove a server group</span></span>|[<span data-ttu-id="6f425-145">Remover um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-145">Remove a Server Group &#40;SQL Server Management Studio&#41;</span></span>](remove-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-146">Exportar informações de servidor registrado</span><span class="sxs-lookup"><span data-stu-id="6f425-146">Export registered server information</span></span>|[<span data-ttu-id="6f425-147">Exportar informações de servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-147">Export Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](export-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-148">Importar informações de servidor registrado</span><span class="sxs-lookup"><span data-stu-id="6f425-148">Import registered server information</span></span>|[<span data-ttu-id="6f425-149">Importar informações de servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-149">Import Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](import-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="6f425-150">Criar um servidor de gerenciamento central e grupo de servidor</span><span class="sxs-lookup"><span data-stu-id="6f425-150">Create a Central Management Server and Server Group</span></span>|[<span data-ttu-id="6f425-151">Criar um servidor de gerenciamento central e um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-151">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-a-central-management-server-and-server-group.md)|  
|<span data-ttu-id="6f425-152">Executar instruções em vários servidores simultaneamente</span><span class="sxs-lookup"><span data-stu-id="6f425-152">Execute statements against multiple servers simultaneously</span></span>|[<span data-ttu-id="6f425-153">Executar instruções em vários servidores simultaneamente &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6f425-153">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](execute-statements-against-multiple-servers-simultaneously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="6f425-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f425-154">See Also</span></span>  
 [<span data-ttu-id="6f425-155">Servidores remotos</span><span class="sxs-lookup"><span data-stu-id="6f425-155">Remote Servers</span></span>](../../database-engine/configure-windows/remote-servers.md)  
  
  
