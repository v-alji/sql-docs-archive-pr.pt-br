---
title: Solução de problemas de usuários órfãos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- orphaned users [SQL Server]
- logins [SQL Server], orphaned users
- troubleshooting [SQL Server], user accounts
- user accounts [SQL Server], orphaned users
- failover [SQL Server], managing metadata
- database mirroring [SQL Server], metadata
- users [SQL Server], orphaned
ms.assetid: 11eefa97-a31f-4359-ba5b-e92328224133
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5df714d818949b921ff2236e50d58913eab0e0db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573582"
---
# <a name="troubleshoot-orphaned-users-sql-server"></a><span data-ttu-id="3698a-102">Solução de problemas de usuários órfãos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3698a-102">Troubleshoot Orphaned Users (SQL Server)</span></span>
  <span data-ttu-id="3698a-103">Para fazer logon em uma instância do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], uma entidade deve ter um logon válido no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3698a-103">To log into an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a principal must have a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3698a-104">Esse logon é usado no processo de autenticação que verifica se a entidade tem permissão para conectar-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3698a-104">This login is used in the authentication process that verifies whether the principal is allowed to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3698a-105">Os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logons em uma instância de servidor são visíveis na exibição de catálogo **sys. server_principals** e na exibição de compatibilidade de **logons dosys.sys** .</span><span class="sxs-lookup"><span data-stu-id="3698a-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins on a server instance are visible in the **sys.server_principals** catalog view and the **sys.syslogins** compatibility view.</span></span>  
  
 <span data-ttu-id="3698a-106">Os logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] acessam bancos de dados individuais usando um usuário do banco de dados mapeado para o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3698a-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins access individual databases using a database user that is mapped to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3698a-107">Há duas exceções a essa regra:</span><span class="sxs-lookup"><span data-stu-id="3698a-107">There are two exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="3698a-108">A conta Convidado.</span><span class="sxs-lookup"><span data-stu-id="3698a-108">The guest account.</span></span>  
  
     <span data-ttu-id="3698a-109">Essa é uma conta que, quando habilitada no banco de dados, habilita os logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não mapeados para um usuário do banco de dados para acessar o banco de dados como um usuário convidado.</span><span class="sxs-lookup"><span data-stu-id="3698a-109">This is an account that, when enabled in the database, enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are not mapped to a database user to enter the database as the guest user.</span></span>  
  
-   <span data-ttu-id="3698a-110">Associação de grupo do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="3698a-110">Microsoft Windows group memberships.</span></span>  
  
     <span data-ttu-id="3698a-111">Um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criado a partir de um usuário do Windows poderá acessar um banco de dados se esse usuário for membro de um grupo do Windows que também seja um usuário no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3698a-111">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login created from a Windows user can enter a database if the Windows user is a member of a Windows group that is also a user in the database.</span></span>  
  
 <span data-ttu-id="3698a-112">Informações sobre o mapeamento de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um usuário do banco de dados são armazenadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3698a-112">Information about the mapping of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to a database user is stored within the database.</span></span> <span data-ttu-id="3698a-113">Isso inclui o nome do usuário do banco de dados e o SID do logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondente.</span><span class="sxs-lookup"><span data-stu-id="3698a-113">It includes the name of the database user and the SID of the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3698a-114">As permissões desse usuário de banco de dados são usadas para autorização no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3698a-114">The permissions of this database user are used for authorization in the database.</span></span>  
  
 <span data-ttu-id="3698a-115">Um usuário de banco de dados para o qual o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondente não está definido ou está definido incorretamente em uma instância do servidor não pode fazer logon na instância.</span><span class="sxs-lookup"><span data-stu-id="3698a-115">A database user for which the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="3698a-116">Esse usuário é um *usuário órfão* do banco de dados nessa instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="3698a-116">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="3698a-117">Um usuário do banco de dados torna-se órfão se o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondente for descartado.</span><span class="sxs-lookup"><span data-stu-id="3698a-117">A database user can become orphaned if the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is dropped.</span></span> <span data-ttu-id="3698a-118">Além disso, um usuário de banco de dados pode se tornar órfão após um banco de dados ser restaurado ou anexado a uma instância diferente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3698a-118">Also, a database user can become orphaned after a database is restored or attached to a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3698a-119">A condição de órfão pode ocorrer se o usuário do banco de dados for mapeado para um SID que não esteja presente na nova instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="3698a-119">Orphaning can happen if the database user is mapped to a SID that is not present in the new server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3698a-120">Um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logon não pode acessar um banco de dados no qual ele não tem um usuário de banco de dados correspondente, a menos que o **convidado** esteja habilitado nesse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3698a-120">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login cannot access a database in which it lacks a corresponding database user unless **guest** is enabled in that database.</span></span> <span data-ttu-id="3698a-121">Para obter informações sobre como criar uma conta de usuário de banco de dados, consulte [Create user &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3698a-121">For information about creating a database user account, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="to-detect-orphaned-users"></a><span data-ttu-id="3698a-122">Para detectar usuários órfãos</span><span class="sxs-lookup"><span data-stu-id="3698a-122">To Detect Orphaned Users</span></span>  
 <span data-ttu-id="3698a-123">Para detectar usuários órfãos, execute as seguintes instruções Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="3698a-123">To detect orphaned users, execute the following Transact-SQL statements:</span></span>  
  
```  
USE <database_name>;  
GO;   
sp_change_users_login @Action='Report';  
GO;  
```  
  
 <span data-ttu-id="3698a-124">A saída lista os usuários e os SIDs (identificadores de segurança) correspondentes no banco de dados atual que não estão vinculados a um logon de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3698a-124">The output lists the users and corresponding security identifiers (SID) in the current database that are not linked to any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="3698a-125">Para obter mais informações, consulte [sp_change_users_login &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3698a-125">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3698a-126">**sp_change_users_login** não pode ser usado com [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logons criados no Windows.</span><span class="sxs-lookup"><span data-stu-id="3698a-126">**sp_change_users_login** cannot be used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are created from Windows.</span></span>  
  
## <a name="to-resolve-an-orphaned-user"></a><span data-ttu-id="3698a-127">Para resolver um usuário órfão</span><span class="sxs-lookup"><span data-stu-id="3698a-127">To Resolve an Orphaned User</span></span>  
 <span data-ttu-id="3698a-128">Para resolver um usuário órfão, use o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="3698a-128">To resolve an orphaned user, use the following procedure:</span></span>  
  
1.  <span data-ttu-id="3698a-129">O comando a seguir revincula a conta de logon do servidor especificada por *<login_name>* com o usuário do banco de dados especificado por \*<database_user \*>.</span><span class="sxs-lookup"><span data-stu-id="3698a-129">The following command relinks the server login account specified by *<login_name>* with the database user specified by *<database_user>*.</span></span>  
  
    ```  
    USE <database_name>;  
    GO  
    sp_change_users_login @Action='update_one', @UserNamePattern='<database_user>', @LoginName='<login_name>';  
    GO  
  
    ```  
  
     <span data-ttu-id="3698a-130">Para obter mais informações, consulte [sp_change_users_login &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3698a-130">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
2.  <span data-ttu-id="3698a-131">Depois que você executar o código na etapa anterior, o usuário poderá acessar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3698a-131">After you run the code in the preceding step, the user can access the database.</span></span> <span data-ttu-id="3698a-132">Em seguida, o usuário pode alterar a senha do *<login_name>* conta de logon usando o procedimento armazenado **sp_password** , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3698a-132">The user then can alter the password of the *<login_name>* login account by using the **sp_password** stored procedure, as follows:</span></span>  
  
    ```  
    USE master   
    GO  
    sp_password @old=NULL, @new='password', @loginame='<login_name>';  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3698a-133">Somente logons com a permissão ALTER ANY LOGIN podem alterar a senha do logon de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="3698a-133">Only logins with the ALTER ANY LOGIN permission can change the password of another user's login.</span></span> <span data-ttu-id="3698a-134">Porém, somente membros da função **sysadmin** podem modificar senhas de membros da função **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3698a-134">However, only members of the **sysadmin** role can modify passwords of **sysadmin** role members.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3698a-135">**sp_password** não pode ser usada para [!INCLUDE[msCoName](../../includes/msconame-md.md)] contas do Windows.</span><span class="sxs-lookup"><span data-stu-id="3698a-135">**sp_password** cannot be used for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows accounts.</span></span> <span data-ttu-id="3698a-136">Usuários que se conectam a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pela da conta de rede do Windows são autenticados pelo Windows; portanto, suas senhas só podem ser alteradas no Windows.</span><span class="sxs-lookup"><span data-stu-id="3698a-136">Users connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through their Windows network account are authenticated by Windows; therefore, their passwords can only be changed in Windows.</span></span>  
  
     <span data-ttu-id="3698a-137">Para obter mais informações, consulte [sp_password &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3698a-137">For more information, see [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3698a-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3698a-138">See Also</span></span>  
 <span data-ttu-id="3698a-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3698a-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="3698a-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3698a-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="3698a-141">[&#41;&#40;Transact-SQL de sp_change_users_login](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3698a-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span></span>  
 <span data-ttu-id="3698a-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3698a-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span></span>  
 <span data-ttu-id="3698a-143">[&#41;&#40;Transact-SQL de sp_grantlogin](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3698a-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span></span>  
 <span data-ttu-id="3698a-144">[&#41;&#40;Transact-SQL de sp_password](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3698a-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span></span>  
 <span data-ttu-id="3698a-145">[sys.sysusuários &#40;&#41;Transact-SQL](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3698a-145">[sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span></span>  
 [<span data-ttu-id="3698a-146">sys.syslogons &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3698a-146">sys.syslogins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql)  
  
  
