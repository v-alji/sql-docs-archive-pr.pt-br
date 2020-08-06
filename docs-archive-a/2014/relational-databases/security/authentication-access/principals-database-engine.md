---
title: Entidades de segurança (mecanismo de banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectroll.f1
- sql12.swb.databaseuser.permissions.user.f1--May use common.permissions
helpviewer_keywords:
- certificates [SQL Server], principals
- roles [SQL Server], principals
- permissions [SQL Server], principals
- '##MS_SQLAuthenticatorCertificate##'
- principals [SQL Server]
- '##MS_SQLResourceSigningCertificate##'
- groups [SQL Server], principals
- '##MS_AgentSigningCertificate##'
- authentication [SQL Server], principals
- schemas [SQL Server], principals
- principals [SQL Server], about principals
- security [SQL Server], principals
- users [SQL Server], principals
- '##MS_SQLReplicationSigningCertificate##'
ms.assetid: 3f7adbf7-6e40-4396-a8ca-71cbb843b5c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 808c8516b3ed9e95ea4c724736461cb00923a7fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583457"
---
# <a name="principals-database-engine"></a><span data-ttu-id="304f5-102">Entidades (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="304f5-102">Principals (Database Engine)</span></span>
  <span data-ttu-id="304f5-103">*Entidades* são entidades que podem solicitar recursos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="304f5-103">*Principals* are entities that can request [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources.</span></span> <span data-ttu-id="304f5-104">Como outros componentes do modelo de autorização do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , as entidades podem ser organizadas em uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="304f5-104">Like other components of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authorization model, principals can be arranged in a hierarchy.</span></span> <span data-ttu-id="304f5-105">O escopo de influência de uma entidade de segurança depende do escopo da definição da entidade de segurança: Windows, servidor, banco de dados e se a entidade de segurança é indivisível ou uma coleção.</span><span class="sxs-lookup"><span data-stu-id="304f5-105">The scope of influence of a principal depends on the scope of the definition of the principal: Windows, server, database; and whether the principal is indivisible or a collection.</span></span> <span data-ttu-id="304f5-106">Um logon do Windows é um exemplo de um principal indivisível, enquanto um Grupo do Windows é um exemplo de um principal que é uma coleção.</span><span class="sxs-lookup"><span data-stu-id="304f5-106">A Windows Login is an example of an indivisible principal, and a Windows Group is an example of a principal that is a collection.</span></span> <span data-ttu-id="304f5-107">Todas as entidades têm um SID (identificador de segurança).</span><span class="sxs-lookup"><span data-stu-id="304f5-107">Every principal has a security identifier (SID).</span></span>  
  
 <span data-ttu-id="304f5-108">**Entidades no nível do Windows**</span><span class="sxs-lookup"><span data-stu-id="304f5-108">**Windows-level principals**</span></span>  
  
-   <span data-ttu-id="304f5-109">Logon de domínio do Windows</span><span class="sxs-lookup"><span data-stu-id="304f5-109">Windows Domain Login</span></span>  
  
-   <span data-ttu-id="304f5-110">Logon local do Windows</span><span class="sxs-lookup"><span data-stu-id="304f5-110">Windows Local Login</span></span>  
  
 <span data-ttu-id="304f5-111">**SQL Server** - **level** **entidades** de nível</span><span class="sxs-lookup"><span data-stu-id="304f5-111">**SQL Server**-**level** **principals**</span></span>  
  
-   <span data-ttu-id="304f5-112">Logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="304f5-112">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Login</span></span>  
  
-   <span data-ttu-id="304f5-113">Função do servidor</span><span class="sxs-lookup"><span data-stu-id="304f5-113">Server Role</span></span>  
  
 <span data-ttu-id="304f5-114">**Entidades no nível do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="304f5-114">**Database-level principals**</span></span>  
  
-   <span data-ttu-id="304f5-115">Usuário de banco de dados</span><span class="sxs-lookup"><span data-stu-id="304f5-115">Database User</span></span>  
  
-   <span data-ttu-id="304f5-116">Função de banco de dados</span><span class="sxs-lookup"><span data-stu-id="304f5-116">Database Role</span></span>  
  
-   <span data-ttu-id="304f5-117">Função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="304f5-117">Application Role</span></span>  
  
## <a name="the-sql-server-sa-login"></a><span data-ttu-id="304f5-118">Logon sa do SQL Server</span><span class="sxs-lookup"><span data-stu-id="304f5-118">The SQL Server sa Login</span></span>  
 <span data-ttu-id="304f5-119">O logon sa do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é uma entidade de segurança no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="304f5-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sa log in is a server-level principal.</span></span> <span data-ttu-id="304f5-120">Por padrão, ele é criado quando uma instância é instalada.</span><span class="sxs-lookup"><span data-stu-id="304f5-120">By default, it is created when an instance is installed.</span></span> <span data-ttu-id="304f5-121">A partir do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], o banco de dados padrão de sa é o mestre.</span><span class="sxs-lookup"><span data-stu-id="304f5-121">Beginning in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the default database of sa is master.</span></span> <span data-ttu-id="304f5-122">Essa é uma alteração de comportamento de versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="304f5-122">This is a change of behavior from earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="public-database-role"></a><span data-ttu-id="304f5-123">Função de banco de dados pública</span><span class="sxs-lookup"><span data-stu-id="304f5-123">public Database Role</span></span>  
 <span data-ttu-id="304f5-124">Cada usuário do banco de dados pertence à função do banco de dados público.</span><span class="sxs-lookup"><span data-stu-id="304f5-124">Every database user belongs to the public database role.</span></span> <span data-ttu-id="304f5-125">Quando permissões específicas não são concedidas ou são negadas a um usuário em um objeto seguro, o usuário herda as permissões concedidas como públicas naquele objeto seguro.</span><span class="sxs-lookup"><span data-stu-id="304f5-125">When a user has not been granted or denied specific permissions on a securable, the user inherits the permissions granted to public on that securable.</span></span>  
  
## <a name="information_schema-and-sys"></a><span data-ttu-id="304f5-126">INFORMATION_SCHEMA e sys</span><span class="sxs-lookup"><span data-stu-id="304f5-126">INFORMATION_SCHEMA and sys</span></span>  
 <span data-ttu-id="304f5-127">Todo o banco de dados inclui duas entidades exibidas como usuários em exibições do catálogo: INFORMATION_SCHEMA e sys.</span><span class="sxs-lookup"><span data-stu-id="304f5-127">Every database includes two entities that appear as users in catalog views: INFORMATION_SCHEMA and sys.</span></span> <span data-ttu-id="304f5-128">Essas entidades são exigidas pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="304f5-128">These entities are required by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="304f5-129">Elas não são entidades, tampouco podem ser modificadas ou descartadas.</span><span class="sxs-lookup"><span data-stu-id="304f5-129">They are not principals, and they cannot be modified or dropped.</span></span>  
  
## <a name="certificate-based-sql-server-logins"></a><span data-ttu-id="304f5-130">Logons do SQL Server com base em certificado</span><span class="sxs-lookup"><span data-stu-id="304f5-130">Certificate-based SQL Server Logins</span></span>  
 <span data-ttu-id="304f5-131">Entidades de servidor com nomes entre duas marcas hash (##) são somente para uso interno do sistema.</span><span class="sxs-lookup"><span data-stu-id="304f5-131">Server principals with names enclosed by double hash marks (##) are for internal system use only.</span></span> <span data-ttu-id="304f5-132">As entidades a seguir são criadas com base em certificados quando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é instalado e não devem ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="304f5-132">The following principals are created from certificates when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is installed, and should not be deleted.</span></span>  
  
-   <span data-ttu-id="304f5-133">\##MS_SQLResourceSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="304f5-133">\##MS_SQLResourceSigningCertificate##</span></span>  
  
-   <span data-ttu-id="304f5-134">\##MS_SQLReplicationSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="304f5-134">\##MS_SQLReplicationSigningCertificate##</span></span>  
  
-   <span data-ttu-id="304f5-135">\##MS_SQLAuthenticatorCertificate##</span><span class="sxs-lookup"><span data-stu-id="304f5-135">\##MS_SQLAuthenticatorCertificate##</span></span>  
  
-   <span data-ttu-id="304f5-136">\##MS_AgentSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="304f5-136">\##MS_AgentSigningCertificate##</span></span>  
  
-   <span data-ttu-id="304f5-137">\##MS_PolicyEventProcessingLogin##</span><span class="sxs-lookup"><span data-stu-id="304f5-137">\##MS_PolicyEventProcessingLogin##</span></span>  
  
-   <span data-ttu-id="304f5-138">\##MS_PolicySigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="304f5-138">\##MS_PolicySigningCertificate##</span></span>  
  
-   <span data-ttu-id="304f5-139">\##MS_PolicyTsqlExecutionLogin##</span><span class="sxs-lookup"><span data-stu-id="304f5-139">\##MS_PolicyTsqlExecutionLogin##</span></span>  
  
## <a name="the-guest-user"></a><span data-ttu-id="304f5-140">O Usuário convidado</span><span class="sxs-lookup"><span data-stu-id="304f5-140">The guest User</span></span>  
 <span data-ttu-id="304f5-141">Cada banco de dados inclui um **convidado**.</span><span class="sxs-lookup"><span data-stu-id="304f5-141">Each database includes a **guest**.</span></span> <span data-ttu-id="304f5-142">As permissões concedidas ao usuário **convidado** são herdadas pelos usuários que têm acesso ao banco de dados, mas que não têm uma conta de usuário no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="304f5-142">Permissions granted to the **guest** user are inherited by users who have access to the database, but who do not have a user account in the database.</span></span> <span data-ttu-id="304f5-143">O usuário **convidado** não pode ser removido, mas pode ser desabilitado por meio da revogação de sua `CONNECT` permissão.</span><span class="sxs-lookup"><span data-stu-id="304f5-143">The **guest** user cannot be dropped, but it can be disabled by revoking it's `CONNECT` permission.</span></span> <span data-ttu-id="304f5-144">A `CONNECT` permissão pode ser revogada executando `REVOKE CONNECT FROM GUEST` em qualquer banco de dados que não seja o mestre ou o tempdb.</span><span class="sxs-lookup"><span data-stu-id="304f5-144">The `CONNECT` permission can be revoked by executing `REVOKE CONNECT FROM GUEST` within any database other than master or tempdb.</span></span>  
  
## <a name="client-and-database-server"></a><span data-ttu-id="304f5-145">Servidor de banco de dados e cliente</span><span class="sxs-lookup"><span data-stu-id="304f5-145">Client and Database Server</span></span>  
 <span data-ttu-id="304f5-146">Por definição, um cliente e um servidor de banco de dados são entidades de segurança e podem ser protegidos.</span><span class="sxs-lookup"><span data-stu-id="304f5-146">By definition, a client and a database server are security principals and can be secured.</span></span> <span data-ttu-id="304f5-147">Essas entidades podem ser autenticadas mutuamente antes que uma conexão de rede segura seja estabelecida.</span><span class="sxs-lookup"><span data-stu-id="304f5-147">These entities can be mutually authenticated before a secure network connection is established.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="304f5-148">dá suporte ao protocolo de autenticação [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) , que define como os clientes interagem com um serviço de autenticação de rede.</span><span class="sxs-lookup"><span data-stu-id="304f5-148">supports the [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) authentication protocol, which defines how clients interact with a network authentication service.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="304f5-149">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="304f5-149">Related Tasks</span></span>  
 <span data-ttu-id="304f5-150">Os tópicos a seguir são incluídos nesta seção dos Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="304f5-150">The following topics are included in this section of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="304f5-151">Tópicos de instruções sobre gerenciamento de logons, usuários e esquemas</span><span class="sxs-lookup"><span data-stu-id="304f5-151">Managing Logins, Users, and Schemas How-to Topics</span></span>](managing-logins-users-and-schemas-how-to-topics.md)  
  
-   [<span data-ttu-id="304f5-152">Funções de nível de servidor</span><span class="sxs-lookup"><span data-stu-id="304f5-152">Server-Level Roles</span></span>](server-level-roles.md)  
  
-   [<span data-ttu-id="304f5-153">Funções de nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="304f5-153">Database-Level Roles</span></span>](database-level-roles.md)  
  
-   [<span data-ttu-id="304f5-154">Funções de aplicativo</span><span class="sxs-lookup"><span data-stu-id="304f5-154">Application Roles</span></span>](application-roles.md)  
  
## <a name="see-also"></a><span data-ttu-id="304f5-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="304f5-155">See Also</span></span>  
 <span data-ttu-id="304f5-156">[Protegendo o SQL Server](../securing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="304f5-156">[Securing SQL Server](../securing-sql-server.md) </span></span>  
 <span data-ttu-id="304f5-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="304f5-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span></span>  
 <span data-ttu-id="304f5-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="304f5-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span></span>  
 <span data-ttu-id="304f5-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="304f5-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span></span>  
 <span data-ttu-id="304f5-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="304f5-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span></span>  
 <span data-ttu-id="304f5-161">[Funções de nível de servidor](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="304f5-161">[Server-Level Roles](server-level-roles.md) </span></span>  
 [<span data-ttu-id="304f5-162">Funções de nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="304f5-162">Database-Level Roles</span></span>](database-level-roles.md)  
  
  
