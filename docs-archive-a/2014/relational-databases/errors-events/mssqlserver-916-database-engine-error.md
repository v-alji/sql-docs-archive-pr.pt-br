---
title: MSSQLSERVER_916 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 916 (Database Engine error)
ms.assetid: 73eb6581-99fe-49a5-9b42-e239d7ffe27f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ee67c1e2f67c3c7903c67082ec3793d9d9820061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573043"
---
# <a name="mssqlserver_916"></a><span data-ttu-id="81df2-102">MSSQLSERVER_916</span><span class="sxs-lookup"><span data-stu-id="81df2-102">MSSQLSERVER_916</span></span>
    
## <a name="details"></a><span data-ttu-id="81df2-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="81df2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81df2-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="81df2-104">Product Name</span></span>|<span data-ttu-id="81df2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="81df2-105">SQL Server</span></span>|  
|<span data-ttu-id="81df2-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="81df2-106">Event ID</span></span>|<span data-ttu-id="81df2-107">916</span><span class="sxs-lookup"><span data-stu-id="81df2-107">916</span></span>|  
|<span data-ttu-id="81df2-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="81df2-108">Event Source</span></span>|<span data-ttu-id="81df2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="81df2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="81df2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="81df2-110">Component</span></span>|<span data-ttu-id="81df2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="81df2-111">SQLEngine</span></span>|  
|<span data-ttu-id="81df2-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="81df2-112">Symbolic Name</span></span>|<span data-ttu-id="81df2-113">NOTUSER</span><span class="sxs-lookup"><span data-stu-id="81df2-113">NOTUSER</span></span>|  
|<span data-ttu-id="81df2-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="81df2-114">Message Text</span></span>|<span data-ttu-id="81df2-115">A entidade de segurança do servidor "%.\*ls" não é capaz de acessar o banco de dados "%.\*ls" no contexto de segurança atual.</span><span class="sxs-lookup"><span data-stu-id="81df2-115">The server principal "%.\*ls" is not able to access the database "%.\*ls" under the current security context.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81df2-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="81df2-116">Explanation</span></span>  
 <span data-ttu-id="81df2-117">O logon não tem permissões suficientes para conectar-se ao banco de dados nomeado.</span><span class="sxs-lookup"><span data-stu-id="81df2-117">The login does not have sufficient permissions to connect to the named database.</span></span> <span data-ttu-id="81df2-118">Os logons que podem conectar-se a essa instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas que não têm permissões específicas em um banco de dados, recebem as permissões do usuário convidado.</span><span class="sxs-lookup"><span data-stu-id="81df2-118">Logins that can connect to this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but that do not have specific permissions in a database receive the permissions of the guest user.</span></span> <span data-ttu-id="81df2-119">Esta é uma medida de segurança para evitar que usuários em um banco de dados se conectem a outros bancos de dados em que não têm privilégios.</span><span class="sxs-lookup"><span data-stu-id="81df2-119">This is a security measure to prevent users in one database from connecting to other databases where they do not have privileges.</span></span> <span data-ttu-id="81df2-120">Esta mensagem de erro pode ocorrer quando o usuário convidado não tem permissão CONNECT para o banco de dados nomeado e a propriedade confiável não está definida.</span><span class="sxs-lookup"><span data-stu-id="81df2-120">This error message can occur when the guest user does not have CONNECT permission to the named database and the trustworthy property is not set.</span></span> <span data-ttu-id="81df2-121">Essa mensagem de erro poderá ser exibida quando o usuário convidado não tiver a permissão CONNECT para o banco de dados nomeado.</span><span class="sxs-lookup"><span data-stu-id="81df2-121">This error message can occur when the guest user does not have CONNECT permission to the named database.</span></span>  
  
 <span data-ttu-id="81df2-122">Quando a permissão CONNECT para o banco de dados msdb for negada ou revogada, o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] poderá receber esse erro quando o Pesquisador de Objetos tentar mostrar o status do gerenciamento baseado em políticas de cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="81df2-122">When CONNECT permission to the msdb database is denied or revoked, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] can receive this error when Object Explorer tries to show the Policy Based Management status of each database.</span></span> <span data-ttu-id="81df2-123">O Pesquisador de Objetos usa as permissões do logon atual para consultar o banco de dados msdb quanto a essas informações, o que causa o erro.</span><span class="sxs-lookup"><span data-stu-id="81df2-123">Object Explorer uses the permissions of the current login to query the msdb database for this information, which causes the error.</span></span> <span data-ttu-id="81df2-124">A seguinte mensagem de erro também ocorre:</span><span class="sxs-lookup"><span data-stu-id="81df2-124">The following error message also occurs:</span></span>  
  
 <span data-ttu-id="81df2-125">Falha ao recuperar dados para esta solicitação.</span><span class="sxs-lookup"><span data-stu-id="81df2-125">Failed to retrieve data for this request.</span></span> <span data-ttu-id="81df2-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span><span class="sxs-lookup"><span data-stu-id="81df2-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81df2-127">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="81df2-127">User Action</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="81df2-128">Para evitar esta medida de segurança, verifique se há uma compreensão clara sobre a autenticação de usuários em diversos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="81df2-128">Before circumventing this security measure be sure to have a clear understanding of users are authenticated in various databases.</span></span> <span data-ttu-id="81df2-129">Os métodos a seguir talvez permitam que usuários tenham permissões em um banco de dados para se conectarem a outros bancos de dados que podem expor os dados a um usuário mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="81df2-129">The following methods may allow users that have permissions in one database to connect to other databases which could expose data to a malicious user.</span></span> <span data-ttu-id="81df2-130">Quando os bancos de dados independentes são habilitados, as etapas a seguir podem permitir proprietários de banco de dados em um banco de dados para conceder acesso a outro banco de dados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81df2-130">When contained databases are enabled, the following steps can allow database owners in one database to grant access to other database on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="81df2-131">Você pode se conectar ao banco de dados de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="81df2-131">You can connect to the database in one of the following ways:</span></span>  
  
-   <span data-ttu-id="81df2-132">Concedendo ao logon específico acesso ao banco de dados nomeado.</span><span class="sxs-lookup"><span data-stu-id="81df2-132">Grant the specific login access to the named database.</span></span> <span data-ttu-id="81df2-133">O exemplo a seguir concede ao logon `Adventure-Works\Larry` acesso ao banco de dados `msdb`.</span><span class="sxs-lookup"><span data-stu-id="81df2-133">The following example grants the login `Adventure-Works\Larry` access to the `msdb` database.</span></span>  
  
     <span data-ttu-id="81df2-134">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="81df2-134">USE msdb ;</span></span>  
  
     <span data-ttu-id="81df2-135">GO</span><span class="sxs-lookup"><span data-stu-id="81df2-135">GO</span></span>  
  
     <span data-ttu-id="81df2-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span><span class="sxs-lookup"><span data-stu-id="81df2-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span></span>  
  
-   <span data-ttu-id="81df2-137">Concedendo a permissão CONNECT ao banco de dados nomeado na mensagem de erro para o usuário convidado.</span><span class="sxs-lookup"><span data-stu-id="81df2-137">Grant the CONNECT permission to the database named in the error message for the guest user.</span></span> <span data-ttu-id="81df2-138">O exemplo a seguir concede a permissão `CONNECT` ao banco de dados `msdb` para o usuário `guest`.</span><span class="sxs-lookup"><span data-stu-id="81df2-138">The following example grants the `CONNECT` permission to the `msdb` database for the user `guest`.</span></span>  
  
     <span data-ttu-id="81df2-139">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="81df2-139">USE msdb ;</span></span>  
  
     <span data-ttu-id="81df2-140">GO</span><span class="sxs-lookup"><span data-stu-id="81df2-140">GO</span></span>  
  
     <span data-ttu-id="81df2-141">GRANT CONNECT TO guest ;</span><span class="sxs-lookup"><span data-stu-id="81df2-141">GRANT CONNECT TO guest ;</span></span>  
  
-   <span data-ttu-id="81df2-142">Habilite a propriedade TRUSTWORTHY no banco de dados que tem o usuário autenticado.</span><span class="sxs-lookup"><span data-stu-id="81df2-142">Enable the TRUSTWORTHY property on the database that has authenticated the user.</span></span>  
  
     `ALTER DATABASE AdventureWorks SET TRUSTWORTHY ON;`  
  
  
