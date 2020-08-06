---
title: Ajuda do SQL Server Configuration Manager | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, help
ms.assetid: 6e909911-39a6-469b-b22a-3afdfd08a30b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10a6d6052fe109892f975774a1ed65b818ef0581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683854"
---
# <a name="sql-server-configuration-manager-help"></a><span data-ttu-id="32dc0-102">Ajuda do SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="32dc0-102">SQL Server Configuration Manager Help</span></span>
  <span data-ttu-id="32dc0-103">Use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para configurar os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e configurar a conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="32dc0-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and configure network connectivity.</span></span> <span data-ttu-id="32dc0-104">Para criar ou gerenciar objetos de banco de dados, configurar a segurança e escrever consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] , use o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32dc0-104">To create or manage database objects, configure security, and write [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="32dc0-105">Para obter mais informações sobre o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consulte os Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32dc0-105">For more information about [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="32dc0-106">Esta seção contém os tópicos da Ajuda F1 para as caixas de diálogo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="32dc0-106">This section contains the F1 Help topics for the dialogs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32dc0-107">O Configuration Manager [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode configurar versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores à [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32dc0-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager cannot configure versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="services"></a><span data-ttu-id="32dc0-108">Serviços</span><span class="sxs-lookup"><span data-stu-id="32dc0-108">Services</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="32dc0-109">Configuration Manager gerencia serviços relacionados ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32dc0-109">Configuration Manager manages services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="32dc0-110">Embora muitas dessas tarefas possam ser realizadas com a caixa de diálogo Serviços do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, é importante observar que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager executa operações adicionais nos serviços que gerencia, como aplicar as permissões corretas quando a conta do serviço é alterada.</span><span class="sxs-lookup"><span data-stu-id="32dc0-110">Although many of these tasks can be accomplished using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services dialog, is important to note that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager performs additional operations on the services it manages, such as applying the correct permissions when the service account is changed.</span></span> <span data-ttu-id="32dc0-111">O uso da caixa de diálogo normal Serviços do Windows para configurar quaisquer serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] poderia prejudicar o funcionamento do serviço.</span><span class="sxs-lookup"><span data-stu-id="32dc0-111">Using the normal Windows Services dialog to configure any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services might cause the service to malfunction.</span></span>  
  
 <span data-ttu-id="32dc0-112">Use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para as seguintes tarefas de serviços:</span><span class="sxs-lookup"><span data-stu-id="32dc0-112">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks for services:</span></span>  
  
-   <span data-ttu-id="32dc0-113">Iníciar, parar e pausar serviços</span><span class="sxs-lookup"><span data-stu-id="32dc0-113">Start, stop, and pause services</span></span>  
  
-   <span data-ttu-id="32dc0-114">Configurar serviços para iniciar automática ou manualmente, desabilitar os serviços ou alterar outras configurações de serviço</span><span class="sxs-lookup"><span data-stu-id="32dc0-114">Configure services to start automatically or manually, disable the services, or change other service settings</span></span>  
  
-   <span data-ttu-id="32dc0-115">Alterar as senhas das contas usadas pelos serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32dc0-115">Change the passwords for the accounts used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services</span></span>  
  
-   <span data-ttu-id="32dc0-116">Iniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando sinalizadores de rastreamento (parâmetros de linha de comando)</span><span class="sxs-lookup"><span data-stu-id="32dc0-116">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using trace flags (command line parameters)</span></span>  
  
-   <span data-ttu-id="32dc0-117">Exibir as propriedades dos serviços</span><span class="sxs-lookup"><span data-stu-id="32dc0-117">View the properties of services</span></span>  
  
## <a name="sql-server-network-configuration"></a><span data-ttu-id="32dc0-118">Configuração de rede do SQL Server</span><span class="sxs-lookup"><span data-stu-id="32dc0-118">SQL Server Network Configuration</span></span>  
 <span data-ttu-id="32dc0-119">Use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para as seguintes tarefas relacionadas aos serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neste computador:</span><span class="sxs-lookup"><span data-stu-id="32dc0-119">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services on this computer:</span></span>  
  
-   <span data-ttu-id="32dc0-120">Habilitar ou desabilitar um protocolo de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32dc0-120">Enable or disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
-   <span data-ttu-id="32dc0-121">Configurar um protocolo de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32dc0-121">Configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32dc0-122">Para obter um breve tutorial sobre como configurar protocolos e conectar-se ao [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], consulte [Tutorial: Introdução ao mecanismo de banco de dados](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="32dc0-122">For a short tutorial about how to configure protocols and connect to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], see [Tutorial: Getting Started with the Database Engine](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span></span>  
  
## <a name="sql-server-native-client-configuration"></a><span data-ttu-id="32dc0-123">Configuração do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="32dc0-123">SQL Server Native Client Configuration</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="32dc0-124">se conectam ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a biblioteca de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="32dc0-124">clients connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client network library.</span></span> <span data-ttu-id="32dc0-125">Use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para as seguintes tarefas relacionadas aos aplicativos clientes neste computador:</span><span class="sxs-lookup"><span data-stu-id="32dc0-125">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to client applications on this computer:</span></span>  
  
-   <span data-ttu-id="32dc0-126">Para aplicativos cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neste computador, especifique a ordem dos protocolos, ao conectar instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32dc0-126">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications on this computer, specify the protocol order, when connecting to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="32dc0-127">Configure protocolos de conexão de cliente.</span><span class="sxs-lookup"><span data-stu-id="32dc0-127">Configure client connection protocols.</span></span>  
  
-   <span data-ttu-id="32dc0-128">Para aplicativos cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , crie aliases para instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], para que os clientes possam se conectar usando uma cadeia de conexão padrão.</span><span class="sxs-lookup"><span data-stu-id="32dc0-128">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications, create aliases for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so that clients can connect using a custom connection string.</span></span>  
  
 <span data-ttu-id="32dc0-129">Para obter mais informações sobre cada uma dessas tarefas, consulte a ajuda F1 de cada tarefa.</span><span class="sxs-lookup"><span data-stu-id="32dc0-129">For more information about each of these tasks, see F1 help for each task.</span></span>  
  
#### <a name="to-open-sql-server-configuration-manager"></a><span data-ttu-id="32dc0-130">Para abrir o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="32dc0-130">To open SQL Server Configuration Manager</span></span>  
  
-   <span data-ttu-id="32dc0-131">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para **Microsoft SQL Server** (versão), aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="32dc0-131">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server** (version), point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32dc0-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32dc0-132">See Also</span></span>  
 <span data-ttu-id="32dc0-133">[Serviços SQL Servers](../../../2014/tools/configuration-manager/sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="32dc0-133">[SQL Server Services](../../../2014/tools/configuration-manager/sql-server-services.md) </span></span>  
 <span data-ttu-id="32dc0-134">[Configuração de rede SQL Server](sql-server-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="32dc0-134">[SQL Server Network Configuration](sql-server-network-configuration.md) </span></span>  
 <span data-ttu-id="32dc0-135">[Configuração do SQL Native Client 11,0](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="32dc0-135">[SQL Native Client 11.0 Configuration](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span></span>  
 [<span data-ttu-id="32dc0-136">Escolhendo um protocolo de rede</span><span class="sxs-lookup"><span data-stu-id="32dc0-136">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
