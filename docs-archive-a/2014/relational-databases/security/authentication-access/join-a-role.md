---
title: Unir uma função | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.MEMBERSHIP.F1
helpviewer_keywords:
- adding a member to a role
- join a role
ms.assetid: 05c8d10d-5823-46c6-8b1a-81722da6a42b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 58e8c071672c8c3afba8d6c424488899dcf76be7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570569"
---
# <a name="join-a-role"></a><span data-ttu-id="67a3f-102">unir uma função</span><span class="sxs-lookup"><span data-stu-id="67a3f-102">Join a Role</span></span>
  <span data-ttu-id="67a3f-103">Este tópico descreve como atribuir funções a logons e usuários de banco de dados no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67a3f-103">This topic describes how to assign roles to logins and database users in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="67a3f-104">Use funções em [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para gerenciar permissões de maneira eficiente.</span><span class="sxs-lookup"><span data-stu-id="67a3f-104">Use roles in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to efficiently manage permissions.</span></span> <span data-ttu-id="67a3f-105">Atribua permissões a funções e adicione e remova usuários e logons de funções.</span><span class="sxs-lookup"><span data-stu-id="67a3f-105">Assign permissions to roles, and then add and remove users and logins to the roles.</span></span> <span data-ttu-id="67a3f-106">Com o uso de funções, as permissões não precisam ser mantidas individualmente para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="67a3f-106">By using roles, permissions do not have to be individually maintained for each user.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="67a3f-107">dá suporte a quatro tipos de função.</span><span class="sxs-lookup"><span data-stu-id="67a3f-107">supports four types of roles.</span></span>  
  
-   <span data-ttu-id="67a3f-108">Funções de servidor fixas</span><span class="sxs-lookup"><span data-stu-id="67a3f-108">Fixed server roles</span></span>  
  
-   <span data-ttu-id="67a3f-109">Funções de servidor definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="67a3f-109">User-defined server roles</span></span>  
  
-   <span data-ttu-id="67a3f-110">Funções de banco de dados fixas</span><span class="sxs-lookup"><span data-stu-id="67a3f-110">Fixed database roles</span></span>  
  
-   <span data-ttu-id="67a3f-111">Funções de banco de dados definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="67a3f-111">User-defined database roles</span></span>  
  
 <span data-ttu-id="67a3f-112">As funções fixas estão automaticamente disponíveis no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67a3f-112">The fixed roles are automatically available in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="67a3f-113">Funções fixas têm as permissões necessárias para realizar tarefas comuns.</span><span class="sxs-lookup"><span data-stu-id="67a3f-113">Fixed roles have the necessary permissions to accomplish common tasks.</span></span> <span data-ttu-id="67a3f-114">Para obter mais informações sobre funções fixas, consulte os links a seguir.</span><span class="sxs-lookup"><span data-stu-id="67a3f-114">For more information about fixed roles, see the following links.</span></span> <span data-ttu-id="67a3f-115">Funções definidas pelo usuário são criadas por você e podem ser personalizadas com as permissões que você seleciona.</span><span class="sxs-lookup"><span data-stu-id="67a3f-115">User-defined roles are created by you, and can be customized with the permissions that you select.</span></span> <span data-ttu-id="67a3f-116">Para obter mais informações sobre funções definidas pelo usuário, consulte os links a seguir.</span><span class="sxs-lookup"><span data-stu-id="67a3f-116">For more information about user-defined roles, see the following links.</span></span>  
  
 <span data-ttu-id="67a3f-117">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="67a3f-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="67a3f-118">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="67a3f-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="67a3f-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="67a3f-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="67a3f-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="67a3f-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="67a3f-121">**Para atribuir funções a logons e usuários de banco de dados, usando:**</span><span class="sxs-lookup"><span data-stu-id="67a3f-121">**To assign roles to logins and database users, using:**</span></span>  
  
     [<span data-ttu-id="67a3f-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67a3f-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="67a3f-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="67a3f-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="67a3f-124">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="67a3f-124">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="67a3f-125">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="67a3f-125">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="67a3f-126">A alteração do nome de uma função de banco de dados não altera o número da ID, o proprietário ou as permissões da função.</span><span class="sxs-lookup"><span data-stu-id="67a3f-126">Changing the name of a database role does not change ID number, owner, or permissions of the role.</span></span>  
  
-   <span data-ttu-id="67a3f-127">As funções de banco de dados são visíveis nas exibições do catálogo sys.database_role_members e sys.database_principals.</span><span class="sxs-lookup"><span data-stu-id="67a3f-127">Database roles are visible in the sys.database_role_members and sys.database_principals catalog views.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="67a3f-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="67a3f-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="67a3f-129">Permissões</span><span class="sxs-lookup"><span data-stu-id="67a3f-129">Permissions</span></span>  
 <span data-ttu-id="67a3f-130">Requer `ALTER ANY ROLE` a permissão no banco de dados, `ALTER` a permissão na função ou a associação em **db_securityadmin**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-130">Requires `ALTER ANY ROLE` permission on the database, `ALTER` permission on the role, or membership in **db_securityadmin**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="67a3f-131">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67a3f-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="67a3f-132">Para adicionar um membro a uma função de servidor fixa</span><span class="sxs-lookup"><span data-stu-id="67a3f-132">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="67a3f-133">No Pesquisador de Objetos, expanda o servidor no qual você quer editar uma função de servidor fixa.</span><span class="sxs-lookup"><span data-stu-id="67a3f-133">In Object Explorer, expand the server in which you want to edit a fixed server role.</span></span>  
  
2.  <span data-ttu-id="67a3f-134">Expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="67a3f-134">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="67a3f-135">Expanda a pasta **Funções de Servidor**</span><span class="sxs-lookup"><span data-stu-id="67a3f-135">Expand the **Server Roles** folder</span></span>  
  
4.  <span data-ttu-id="67a3f-136">Clique com o botão direito do mouse na função que você deseja editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-136">Right-click the role you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="67a3f-137">Na caixa de diálogo **Propriedades da função de servidor –**_server_role_name_ , na página **Membros** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-137">In the **Server Role Properties -**_server_role_name_ dialog box, on the **Members** page, click **Add**.</span></span>  
  
6.  <span data-ttu-id="67a3f-138">Na caixa de diálogo **Selecionar Logon ou Função de Servidor** , em **Digite os nomes de objeto a selecionar (exemplos)** , insira o logon ou função de servidor para adicionar a esta função de servidor.</span><span class="sxs-lookup"><span data-stu-id="67a3f-138">In the **Select Server Login or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or server role to add to this server role.</span></span> <span data-ttu-id="67a3f-139">Como alternativa, clique em **Procurar...** e selecione um ou todos os objetos disponíveis na caixa de diálogo **Procurar objetos**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-139">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="67a3f-140">Clique em **OK** para retornar à caixa de diálogo **Propriedades da função de servidor –**_server_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="67a3f-140">Click **OK** to return to the **Server Role Properties -**_server_role_name_ dialog box.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="67a3f-141">Para adicionar um membro a uma função de banco de dados definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="67a3f-141">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="67a3f-142">No Pesquisador de Objetos, expanda o servidor no qual você quer editar uma função de banco de dados definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="67a3f-142">In Object Explorer, expand the server in which you want to edit a user-defined database role.</span></span>  
  
2.  <span data-ttu-id="67a3f-143">Expanda a pasta **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="67a3f-143">Expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="67a3f-144">Expanda o banco de dados no qual você quer editar uma função de banco de dados definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="67a3f-144">Expand the database in which you want to edit a user-defined database role.</span></span>  
  
4.  <span data-ttu-id="67a3f-145">Expanda a pasta **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="67a3f-145">Expand the **Security** folder.</span></span>  
  
5.  <span data-ttu-id="67a3f-146">Expanda a pasta **Funções** .</span><span class="sxs-lookup"><span data-stu-id="67a3f-146">Expand the **Roles** folder.</span></span>  
  
6.  <span data-ttu-id="67a3f-147">Expanda a pasta **Funções de Servidor** .</span><span class="sxs-lookup"><span data-stu-id="67a3f-147">Expand the **Server Roles** folder.</span></span>  
  
7.  <span data-ttu-id="67a3f-148">Clique com o botão direito do mouse na função que você deseja editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-148">Right-click the role you want to edit and select **Properties**.</span></span>  
  
8.  <span data-ttu-id="67a3f-149">Na caixa de diálogo **Propriedades da função de banco de dados –**_database_role_name_ , na página **geral** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-149">In the **Database Role Properties -**_database_role_name_ dialog box, in the **General** page, click **Add**.</span></span>  
  
9. <span data-ttu-id="67a3f-150">Na caixa de diálogo **Selecionar Usuário ou Função do Banco de Dados** , em **Digite os nomes de objeto a selecionar (exemplos)** , insira o logon ou função de banco de dados para adicionar a esta função de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="67a3f-150">In the **Select Database User or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or database role to add to this database role.</span></span> <span data-ttu-id="67a3f-151">Como alternativa, clique em **Procurar...** e selecione um ou todos os objetos disponíveis na caixa de diálogo **Procurar objetos**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-151">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="67a3f-152">Clique em **OK** para retornar à caixa de diálogo **Propriedades da função de banco de dados –**_database_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="67a3f-152">Click **OK** to return to the **Database Role Properties -**_database_role_name_ dialog box.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="67a3f-153">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="67a3f-153">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="67a3f-154">Para adicionar um membro a uma função de servidor fixa</span><span class="sxs-lookup"><span data-stu-id="67a3f-154">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="67a3f-155">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67a3f-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="67a3f-156">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-156">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="67a3f-157">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-157">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER SERVER ROLE diskadmin ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="67a3f-158">Para obter mais informações, veja [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="67a3f-158">For more information, see [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span></span>  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="67a3f-159">Para adicionar um membro a uma função de banco de dados definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="67a3f-159">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="67a3f-160">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67a3f-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="67a3f-161">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="67a3f-162">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="67a3f-162">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER ROLE Marketing ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="67a3f-163">Para obter mais informações, consulte [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="67a3f-163">For more information, see [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a3f-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67a3f-164">See Also</span></span>  
 <span data-ttu-id="67a3f-165">[Funções de nível de servidor](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="67a3f-165">[Server-Level Roles](server-level-roles.md) </span></span>  
 <span data-ttu-id="67a3f-166">[Funções de nível de banco de dados](../authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="67a3f-166">[Database-Level Roles](../authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="67a3f-167">Funções de aplicativo</span><span class="sxs-lookup"><span data-stu-id="67a3f-167">Application Roles</span></span>](../authentication-access/application-roles.md)  
  
  
