---
title: Conectar-se a qualquer componente de SQL Server da SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cd3e185ea6f289a2a6db46cdca2cb310fefbcf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681355"
---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a><span data-ttu-id="f1cc5-102">Conectar a qualquer componente do SQL Server a partir do SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1cc5-102">Connect to Any SQL Server Component from SQL Server Management Studio</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="f1cc5-103">fornece funcionalidade para gerenciar todos os componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1cc5-103">provides functionality for managing every component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f1cc5-104">Use o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para se conectar a:</span><span class="sxs-lookup"><span data-stu-id="f1cc5-104">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to connect to:</span></span>  
  
-   <span data-ttu-id="f1cc5-105">Uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1cc5-105">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="f1cc5-106">.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-106">.</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]<span data-ttu-id="f1cc5-107">.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-107">.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="f1cc5-108">.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-108">.</span></span>  
  
 <span data-ttu-id="f1cc5-109">Apesar de o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] permitir que você trabalhe com consultas sem primeiro estabelecer uma conexão com uma fonte de dados, a maioria das outras tarefas requer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-109">Although [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] allows you to work with queries without first establishing a connection to a data source, most other tasks require a connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="f1cc5-110">fornece a caixa de diálogo **Conectar ao Servidor** para configurar propriedades de conexão com componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1cc5-110">provides the **Connect to Server** dialog box to configure connection properties to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="f1cc5-111">Quando o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] é iniciado, a caixa de diálogo **Conectar ao Servidor** é exibida e solicita a conexão com um servidor.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-111">When [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] starts, it opens the **Connect to Server** dialog box and prompts you to connect to a server.</span></span> <span data-ttu-id="f1cc5-112">A caixa de diálogo **Conectar ao Servidor** retém as configurações de conexão da última vez que foi utilizada.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-112">The **Connect to Server** dialog box retains the connection settings from the last time it was used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1cc5-113">Esse recurso pode ser desativado de forma que nenhuma conexão seja iniciada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-113">This feature can be turned off so no connection is automatically initiated.</span></span> <span data-ttu-id="f1cc5-114">Para obter mais informações, consulte [Opções de inicialização do serviço Mecanismo de Banco de Dados](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="f1cc5-114">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
## <a name="saving-connections"></a><span data-ttu-id="f1cc5-115">salvando conexões</span><span class="sxs-lookup"><span data-stu-id="f1cc5-115">Saving Connections</span></span>  
 <span data-ttu-id="f1cc5-116">Você pode salvar conexões com servidores específicos em Servidores Registrados ou pode salvar conexões em projetos com o Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-116">You can save connections to specific servers in Registered Servers, or you can save connections in projects with Solution Explorer.</span></span>  
  
### <a name="saving-connections-in-registered-servers"></a><span data-ttu-id="f1cc5-117">Salvando conexões em Servidores Registrados</span><span class="sxs-lookup"><span data-stu-id="f1cc5-117">Saving Connections in Registered Servers</span></span>  
 <span data-ttu-id="f1cc5-118">Ao registrar um servidor, o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] salva as informações de conexão em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-118">When you register a server, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] saves the connection information in Registered Servers.</span></span> <span data-ttu-id="f1cc5-119">Para conectar a um servidor registrado, clique duas vezes no nome do servidor em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-119">To connect to a registered server, double-click the server name in Registered Servers.</span></span> <span data-ttu-id="f1cc5-120">O Pesquisador de Objetos abre uma conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-120">Object Explorer then opens a connection to the server.</span></span>  
  
### <a name="saving-connections-in-solution-explorer"></a><span data-ttu-id="f1cc5-121">Salvando conexões no Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="f1cc5-121">Saving Connections in Solution Explorer</span></span>  
 <span data-ttu-id="f1cc5-122">O Gerenciador de Soluções permite o armazenamento de consultas relacionadas, scripts, conexões e outras informações associadas em um projeto.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-122">Solution Explorer allows you to store related queries, scripts, connections, and other associated information in a project.</span></span> <span data-ttu-id="f1cc5-123">Cada projeto de script contém um nó denominado **Conexões**, no qual você pode salvar uma ou mais conexões.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-123">Each script project contains a node called **Connections**, where you can save one or more connections.</span></span> <span data-ttu-id="f1cc5-124">Para adicionar uma conexão, clique com o botão direito do mouse em **Conexões**e clique em **Nova Conexão**.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-124">To add a connection, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="f1cc5-125">Para acessar uma conexão salva, expanda **Conexões** e clique duas vezes na conexão.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-125">To access a saved connection, expand **Connections** and double-click the connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="f1cc5-126">abre uma janela de consulta associada àquela conexão.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-126">opens a query window associated with that connection.</span></span> <span data-ttu-id="f1cc5-127">Quando salvos, os scripts retêm sua associação com uma conexão específica.</span><span class="sxs-lookup"><span data-stu-id="f1cc5-127">When saved, scripts retain their association to a specific connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cc5-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1cc5-128">See Also</span></span>  
 <span data-ttu-id="f1cc5-129">[Usar SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="f1cc5-129">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="f1cc5-130">Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="f1cc5-130">Object Explorer</span></span>](../object/object-explorer.md)  
  
  
