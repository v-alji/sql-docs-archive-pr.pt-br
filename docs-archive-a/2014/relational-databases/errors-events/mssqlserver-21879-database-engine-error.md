---
title: MSSQLSERVER_21879 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21879 (Database Engine error)
ms.assetid: fcfab735-05ca-423a-89f1-fdee7e2ed8c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 08c5d4f45faf94d555ed7acedd90cc55ec4791ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681668"
---
# <a name="mssqlserver_21879"></a><span data-ttu-id="f6fae-102">MSSQLSERVER_21879</span><span class="sxs-lookup"><span data-stu-id="f6fae-102">MSSQLSERVER_21879</span></span>
    
## <a name="details"></a><span data-ttu-id="f6fae-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f6fae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6fae-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f6fae-104">Product Name</span></span>|<span data-ttu-id="f6fae-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6fae-105">SQL Server</span></span>|  
|<span data-ttu-id="f6fae-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f6fae-106">Event ID</span></span>|<span data-ttu-id="f6fae-107">21879</span><span class="sxs-lookup"><span data-stu-id="f6fae-107">21879</span></span>|  
|<span data-ttu-id="f6fae-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f6fae-108">Event Source</span></span>|<span data-ttu-id="f6fae-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f6fae-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f6fae-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f6fae-110">Component</span></span>|<span data-ttu-id="f6fae-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f6fae-111">SQLEngine</span></span>|  
|<span data-ttu-id="f6fae-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f6fae-112">Symbolic Name</span></span>|<span data-ttu-id="f6fae-113">SQLErrorNum21879</span><span class="sxs-lookup"><span data-stu-id="f6fae-113">SQLErrorNum21879</span></span>|  
|<span data-ttu-id="f6fae-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f6fae-114">Message Text</span></span>|<span data-ttu-id="f6fae-115">Não foi possível consultar o servidor redirecionado '% s' para o publicador original '% s' e o banco de dados publicador '% s' para determinar o nome do servidor remoto; Erro %d, Mensagem de erro '% s.'</span><span class="sxs-lookup"><span data-stu-id="f6fae-115">Unable to query the redirected server '%s' for original publisher '%s' and publisher database '%s' to determine the name of the remote server; Error %d, Error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6fae-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="f6fae-116">Explanation</span></span>  
 <span data-ttu-id="f6fae-117">`sp_validate_redirected_publisher` usa um servidor vinculado temporário criado para se conectar ao publicador redirecionado e descobrir o nome do servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="f6fae-117">`sp_validate_redirected_publisher` uses a temporary linked server that it creates to connect to the redirected publisher in order to discover the name of the remote server.</span></span> <span data-ttu-id="f6fae-118">O erro 21879 é retornado quando a consulta de servidor vinculado falha.</span><span class="sxs-lookup"><span data-stu-id="f6fae-118">Error 21879 is returned when the linked server query fails.</span></span> <span data-ttu-id="f6fae-119">A chamada para solicitar o nome de servidor remoto é normalmente o primeiro uso do servidor vinculado temporário e, portanto, se houver problemas de conectividade, é provável que eles apareçam primeiro com essa chamada.</span><span class="sxs-lookup"><span data-stu-id="f6fae-119">The call to request the remote server name is typically the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with this call.</span></span> <span data-ttu-id="f6fae-120">Essa chamada remota simplesmente executa a seleção de `@@servername` no servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="f6fae-120">This remote call simply executes select `@@servername` at the remote server.</span></span>  
  
 <span data-ttu-id="f6fae-121">O servidor vinculado usado para consultar o publicador redirecionado usa o modo de segurança, logon e senha fornecidos quando `sp_adddistpublisher` foi chamado para o publicador original.</span><span class="sxs-lookup"><span data-stu-id="f6fae-121">The linked server used to query the redirected publisher uses the security mode, login, and password supplied when `sp_adddistpublisher` was called for the original publisher.</span></span>  
  
-   <span data-ttu-id="f6fae-122">Se a autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiver sido usada (modo de segurança 0), o logon e a senha especificados serão usados para a conexão ao servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="f6fae-122">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication was used (security mode 0) then the login and password specified are used to connect to the remote server.</span></span>  
  
-   <span data-ttu-id="f6fae-123">Se a autenticação do Windows tiver sido usada (modo de segurança 1), uma conexão confiável será usada para conectar.</span><span class="sxs-lookup"><span data-stu-id="f6fae-123">If Windows authentication was used (security mode 1) a trusted connection is used for the connection.</span></span>  
  
    -   <span data-ttu-id="f6fae-124">Se `sp_validate_redirected_publisher` for chamado explicitamente por um usuário, o logon de Windows sob o qual o usuário está executando será usado para a conexão.</span><span class="sxs-lookup"><span data-stu-id="f6fae-124">If `sp_validate_redirected_publisher` is called explicitly by a user, the Windows login that the user is running under is used for the connection.</span></span>  
  
    -   <span data-ttu-id="f6fae-125">Se o publicador `sp_validate_redirected_` for chamado por um agente de replicação de `sp_get_redirected_publisher`, o logon do Windows associado ao agente será usado.</span><span class="sxs-lookup"><span data-stu-id="f6fae-125">If `sp_validate_redirected_`publisher is called by a replication agent from `sp_get_redirected_publisher`, the Windows login associated with the agent is used.</span></span>  
  
 <span data-ttu-id="f6fae-126">O erro 21879 pode indicar que `sp_validate_redirected_publisher` foi chamado usando um logon que não é conhecido no publicador de destino redirecionado.</span><span class="sxs-lookup"><span data-stu-id="f6fae-126">Error 21879 can indicate that `sp_validate_redirected_publisher` was called using a login that is not known at the redirected target publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6fae-127">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f6fae-127">User Action</span></span>  
 <span data-ttu-id="f6fae-128">Verifique se o logon de autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o logon de autenticação do Windows é válido em todas as réplicas de grupo de disponibilidade e se tem autorização suficiente para acessar as tabelas de metadados de assinatura (syssubscriptions e sysmergesubscriptions) no banco de dados publicador.</span><span class="sxs-lookup"><span data-stu-id="f6fae-128">Make certain that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication login or the Windows authentication login is valid at all of the availability group replicas and has sufficient authorization to access the subscription metadata tables (syssubscriptions and sysmergesubscriptions) in the publisher database.</span></span>  
  
 <span data-ttu-id="f6fae-129">Existem considerações especiais quando o erro 21879 é retornado de uma chamada a `sp_get_redirected_publisher` iniciada por um agente de replicação executado em um nó diferente do distribuidor; como um agente de mesclagem sendo executado em um assinante.</span><span class="sxs-lookup"><span data-stu-id="f6fae-129">There are special considerations when error 21879 is returned from a call to `sp_get_redirected_publisher` that is initiated by a replication agent running on a node other that the distributor; such as a merge agent running at a subscriber.</span></span> <span data-ttu-id="f6fae-130">Se a autenticação do Windows for usada para a conexão ao publicador redirecionado, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deverá ser configurado para a autenticação Kerberos, para que a conexão seja estabelecida com êxito.</span><span class="sxs-lookup"><span data-stu-id="f6fae-130">If Windows authentication is used for the connection to the redirected publisher, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured for Kerberos authentication for the connection to be successfully established.</span></span> <span data-ttu-id="f6fae-131">Quando a autenticação do Windows é usada e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não é configurado para a autenticação Kerberos, o erro 18456 que indica que o logon 'NT AUTHORITY\ANONYMOUS LOGON' falhou é recebido por um agente de mesclagem executado em um assinante.</span><span class="sxs-lookup"><span data-stu-id="f6fae-131">When Windows authentication is used and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not configured for Kerberos authentication, error 18456 indicating that the 'NT AUTHORITY\ANONYMOUS LOGON' login failed, is received by a merge agent running at a subscriber.</span></span> <span data-ttu-id="f6fae-132">Há três maneiras possíveis de lidar com este problema:</span><span class="sxs-lookup"><span data-stu-id="f6fae-132">There are three possible ways to address this issue:</span></span>  
  
-   <span data-ttu-id="f6fae-133">Configure o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f6fae-133">Configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for Kerberos authentication.</span></span> <span data-ttu-id="f6fae-134">Consulte **Autenticação Kerberos e SQL Server** nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6fae-134">See **Kerberos Authentication and SQL Server** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="f6fae-135">Use `sp_changedistpublisher` para alterar o modo de segurança associado ao Publicador original no MSdistpublishers, bem como para especificar um logon e senha a serem usados para a conexão.</span><span class="sxs-lookup"><span data-stu-id="f6fae-135">Use `sp_changedistpublisher` to change the security mode associated with the original publisher in MSdistpublishers, as well as to specify a login and password to use for the connection.</span></span>  
  
-   <span data-ttu-id="f6fae-136">Especifique o parâmetro de linha de comando *BypassPublisherValidation* na linha de comando do Merge Agent para ignorar a validação quando `sp_get_redirected_publisher` for chamado no distribuidor.</span><span class="sxs-lookup"><span data-stu-id="f6fae-136">Specify the command line parameter *BypassPublisherValidation* on the merge agent command line to bypass validation when `sp_get_redirected_publisher` is called at the distributor.</span></span>  
  
  
