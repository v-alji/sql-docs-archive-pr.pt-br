---
title: Acesso à rede para um ponto de extremidade de espelhamento de banco de dados
description: Saiba como permitir o acesso à rede do Windows authenticatino a um ponto de extremidade de espelhamento de banco de dados para SQL Server.
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 28c8fec5-5feb-4c84-8d72-f2bd1ae3b40d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d1d8786d128ef2cc99fe571e33f89c4c4e7699c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581458"
---
# <a name="allow-network-access-to-a-database-mirroring-endpoint-using-windows-authentication-sql-server"></a><span data-ttu-id="c8538-103">Permitir o acesso à rede a um ponto de extremidade de espelhamento de banco de dados usando a Autenticação do Windows (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c8538-103">Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication (SQL Server)</span></span>
  <span data-ttu-id="c8538-104">O uso da Autenticação do Windows para conectar os pontos de extremidade de espelhamento de banco de dados de duas instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requer a configuração manual de contas de logon sob as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="c8538-104">Using Windows Authentication for connecting the database mirroring endpoints of two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requires manual configuration of login accounts under the following conditions:</span></span>  
  
-   <span data-ttu-id="c8538-105">Se as instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] forem executadas como serviços em diferentes contas de domínio (nos mesmos domínios ou em domínios confiáveis), o logon de cada conta deverá ser criado no **mestre** em cada uma das instâncias de servidor remoto, e esse logon deverá receber permissões CONNECT no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c8538-105">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as services under different domain accounts (in the same or trusted domains), the login of each account must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span>  
  
-   <span data-ttu-id="c8538-106">Se as instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] forem executadas como a conta de Serviço de Rede, o logon da conta de cada computador host (*DomainName***\\***ComputerName$* ) deverá ser criado no **mestre** em cada uma das instâncias de servidor remoto, e esse logon deverá receber permissões CONNECT no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c8538-106">If the instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] run as the Network Service account, the login of the each host computer account (*DomainName***\\***ComputerName$*) must be created in **master** on each of the remote server instances and that login must be granted CONNECT permissions on the endpoint.</span></span> <span data-ttu-id="c8538-107">Isso é porque uma instância de servidor em execução sob a conta de serviço de rede é autenticada usando a conta de domínio do computador host.</span><span class="sxs-lookup"><span data-stu-id="c8538-107">This is because a server instance running under the Network Service account authenticates using the domain account of the host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8538-108">Verifique se há um ponto de extremidade para cada uma das instâncias do servidor.</span><span class="sxs-lookup"><span data-stu-id="c8538-108">Ensure that an endpoint exists for each of the server instances.</span></span> <span data-ttu-id="c8538-109">Para obter mais informações, veja [Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c8538-109">For more information, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
### <a name="to-configure-logins-for-windows-authentication"></a><span data-ttu-id="c8538-110">Para configurar logons para a Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="c8538-110">To configure logins for Windows Authentication</span></span>  
  
1.  <span data-ttu-id="c8538-111">Para a conta de usuário de cada instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], crie um logon nas outras instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8538-111">For the user account of each instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], create a login on the other instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c8538-112">Use a instrução [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) com a cláusula FROM WINDOWS.</span><span class="sxs-lookup"><span data-stu-id="c8538-112">Use a [CREATE LOGIN](/sql/t-sql/statements/create-login-transact-sql) statement with the FROM WINDOWS clause.</span></span>  
  
     <span data-ttu-id="c8538-113">Para obter mais informações, consulte [Crie um logon](../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="c8538-113">For more information, see [Create a Login](../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
2.  <span data-ttu-id="c8538-114">Além disso, para assegurar que o usuário de logon tenha acesso ao ponto de extremidade, use a instrução [GRANT](/sql/t-sql/statements/grant-transact-sql) para conceder permissões de conexão no ponto de extremidade para o logon.</span><span class="sxs-lookup"><span data-stu-id="c8538-114">Also, to ensure that the login user has access to the endpoint, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement to grant connect permissions on the endpoint to the login.</span></span> <span data-ttu-id="c8538-115">Observe que a concessão de permissões de conexão para o ponto de extremidade não é necessária se o usuário for um Administrador.</span><span class="sxs-lookup"><span data-stu-id="c8538-115">Note that granting connect permissions to the endpoint is unnecessary if the user is an Administrator.</span></span>  
  
     <span data-ttu-id="c8538-116">Para obter mais informações, consulte [Conceder uma permissão a uma entidade de segurança](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c8538-116">For more information, see [Grant a Permission to a Principal](../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8538-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c8538-117">Example</span></span>  
 <span data-ttu-id="c8538-118">O exemplo de [!INCLUDE[tsql](../includes/tsql-md.md)] a seguir criar um logon do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para uma conta de usuário denominada `Otheruser` que pertence a um domínio denominado `Adomain`.</span><span class="sxs-lookup"><span data-stu-id="c8538-118">The following [!INCLUDE[tsql](../includes/tsql-md.md)] example creates a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login for a user account named `Otheruser` that belongs to a domain called `Adomain`.</span></span> <span data-ttu-id="c8538-119">O exemplo concede permissões a esse usuário para um ponto de extremidade de espelhamento de banco de dados preexistente denominado `Mirroring_Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="c8538-119">The example then grants this user connect permissions to a pre-existing database mirroring endpoint named `Mirroring_Endpoint`.</span></span>  
  
```  
USE master;  
GO  
CREATE LOGIN [Adomain\Otheruser] FROM WINDOWS;  
GO  
GRANT CONNECT on ENDPOINT::Mirroring_Endpoint TO [Adomain\Otheruser];  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8538-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8538-120">See Also</span></span>  
 <span data-ttu-id="c8538-121">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8538-121">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="c8538-122">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8538-122">[Database Mirroring &#40;SQL Server&#41;](database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c8538-123">[Segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="c8538-123">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](database-mirroring/transport-security-database-mirroring-always-on-availability.md) </span></span>  
 [<span data-ttu-id="c8538-124">O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c8538-124">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
  
  
