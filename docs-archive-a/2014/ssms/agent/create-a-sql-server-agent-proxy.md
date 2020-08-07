---
title: Criar um proxy do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], creating
ms.assetid: 142e0c55-a8b9-4669-be49-b9dc602d5988
author: stevestein
ms.author: sstein
ms.openlocfilehash: a7582aef38d57b15de968d96357e56c1974d733e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576118"
---
# <a name="create-a-sql-server-agent-proxy"></a><span data-ttu-id="60ff3-102">Criar um proxy do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="60ff3-102">Create a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="60ff3-103">Este tópico descreve como criar um proxy do SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60ff3-103">This topic describes how to create a SQL Server Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="60ff3-104">Uma conta proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent define o contexto de segurança no qual uma etapa de trabalho pode ser executada.</span><span class="sxs-lookup"><span data-stu-id="60ff3-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account defines a security context in which a job step can run.</span></span> <span data-ttu-id="60ff3-105">Cada proxy corresponde a uma credencial de segurança.</span><span class="sxs-lookup"><span data-stu-id="60ff3-105">Each proxy corresponds to a security credential.</span></span> <span data-ttu-id="60ff3-106">Para definir as permissões para uma etapa de trabalho em particular, crie um proxy com as permissões necessárias para um subsistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e atribua-o à etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60ff3-106">To set permissions for a particular job step, create a proxy that has the required permissions for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent subsystem, and then assign that proxy to the job step.</span></span>  
  
 <span data-ttu-id="60ff3-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="60ff3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="60ff3-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="60ff3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60ff3-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="60ff3-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="60ff3-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="60ff3-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="60ff3-111">**Para criar um proxy do SQL Server Agent usando:**</span><span class="sxs-lookup"><span data-stu-id="60ff3-111">**To create a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="60ff3-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60ff3-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="60ff3-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60ff3-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60ff3-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="60ff3-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="60ff3-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="60ff3-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="60ff3-116">Primeiro, é necessário criar uma credencial antes de criar um proxy, caso não haja nenhuma disponível.</span><span class="sxs-lookup"><span data-stu-id="60ff3-116">You must create a credential before you create a proxy if one is not already available.</span></span>  
  
-   <span data-ttu-id="60ff3-117">Os proxies do[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent usam credenciais para armazenar informações sobre as contas de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="60ff3-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="60ff3-118">O usuário especificado na credencial deve ter a permissão "Fazer logon como trabalho em lotes" no computador que executa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60ff3-118">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="60ff3-119">Agent verifica o acesso a subsistemas de um proxy e fornece acesso ao proxy sempre que a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="60ff3-119">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="60ff3-120">Se o proxy já não tiver acesso ao subsistema, a etapa de trabalho falhará.</span><span class="sxs-lookup"><span data-stu-id="60ff3-120">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="60ff3-121">Caso contrário, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent representará o usuário especificado no proxy e executará a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60ff3-121">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="60ff3-122">A criação de um proxy não altera as permissões do usuário especificado na credencial do proxy.</span><span class="sxs-lookup"><span data-stu-id="60ff3-122">Creation of a proxy does not change the permissions for the user that is specified in the credential for the proxy.</span></span> <span data-ttu-id="60ff3-123">Por exemplo, você pode criar um proxy para um usuário que não tem permissão de se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60ff3-123">For example, you can create a proxy for a user that does not have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60ff3-124">Nesse caso, as etapas de trabalho que usarem esse proxy não conseguirão se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60ff3-124">In this case, job steps that use that proxy are unable to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="60ff3-125">Se o logon do usuário tiver acesso ao proxy ou se o usuário pertencer a alguma função com acesso ao proxy, ele poderá utilizá-lo em uma etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60ff3-125">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60ff3-126">Segurança</span><span class="sxs-lookup"><span data-stu-id="60ff3-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60ff3-127">Permissões</span><span class="sxs-lookup"><span data-stu-id="60ff3-127">Permissions</span></span>  
  
-   <span data-ttu-id="60ff3-128">Apenas membros da função de servidor fixa **sysadmin** têm permissão para criar, modificar ou excluir contas proxy.</span><span class="sxs-lookup"><span data-stu-id="60ff3-128">Only members of the **sysadmin** fixed server role have permission to create, modify, or delete proxy accounts.</span></span> <span data-ttu-id="60ff3-129">Usuários que não sejam membros da função de servidor fixa **sysadmin** devem ser adicionados a uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** para poderem usar proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**ou **SQLAgentOperatorRole**.</span><span class="sxs-lookup"><span data-stu-id="60ff3-129">Users who are not members of the **sysadmin** fixed server role must be added to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database to use proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**, or **SQLAgentOperatorRole**.</span></span>  
  
-   <span data-ttu-id="60ff3-130">Requer a permissão `ALTER ANY CREDENTIAL` para criar uma credencial além do proxy.</span><span class="sxs-lookup"><span data-stu-id="60ff3-130">Requires `ALTER ANY CREDENTIAL` permission if creating a credential in addition to the proxy.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60ff3-131">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60ff3-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="60ff3-132">Para criar um proxy do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="60ff3-132">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="60ff3-133">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar um proxy no SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="60ff3-133">In **Object Explorer**, click the plus sign to expand the server where you want to create a proxy on SQL Server Agent.</span></span>  
  
2.  <span data-ttu-id="60ff3-134">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="60ff3-134">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="60ff3-135">Clique com o botão direito do mouse na pasta **Proxies** e selecione **Novo Proxy**.</span><span class="sxs-lookup"><span data-stu-id="60ff3-135">Right-click the **Proxies** folder and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="60ff3-136">Na caixa de diálogo **Nova Conta Proxy** , na página **Geral** , digite o nome da nova conta proxy na caixa **Nome do proxy** .</span><span class="sxs-lookup"><span data-stu-id="60ff3-136">On the **New Proxy Account** dialog box, on the **General** page, enter the name of the proxy account in the **Proxy name** box.</span></span>  
  
5.  <span data-ttu-id="60ff3-137">Na caixa de diálogo **Nome da credencial** , digite o nome da credencial de segurança que a conta proxy usará.</span><span class="sxs-lookup"><span data-stu-id="60ff3-137">In the **Credential name** box, enter the name of the security credential that the proxy account will use.</span></span>  
  
6.  <span data-ttu-id="60ff3-138">Na caixa **Descrição** , digite uma descrição da conta proxy.</span><span class="sxs-lookup"><span data-stu-id="60ff3-138">In the **Description** box, enter a description for the proxy account</span></span>  
  
7.  <span data-ttu-id="60ff3-139">Em **Ativo nos seguintes subsistemas**, selecione o subsistema ou os subsistemas apropriados para esse proxy.</span><span class="sxs-lookup"><span data-stu-id="60ff3-139">Under **Active to the following subsystems**, select the appropriate subsystem or subsystems for this proxy.</span></span>  
  
8.  <span data-ttu-id="60ff3-140">Na página **Entidades** , adicione ou remova logons ou funções para conceder ou remover acesso à conta proxy.</span><span class="sxs-lookup"><span data-stu-id="60ff3-140">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
9. <span data-ttu-id="60ff3-141">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60ff3-141">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="60ff3-142">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60ff3-142">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="60ff3-143">Para criar um proxy do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="60ff3-143">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="60ff3-144">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60ff3-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="60ff3-145">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="60ff3-145">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="60ff3-146">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="60ff3-146">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates credential CatalogApplicationCredential  
    USE msdb ;  
    GO  
    CREATE CREDENTIAL CatalogApplicationCredential WITH IDENTITY = 'REDMOND/TestUser',   
        SECRET = 'G3$1o)lkJ8HNd!';  
    GO  
    -- creates proxy "Catalog application proxy" and assigns the credential 'CatalogApplicationCredential' to it.  
    EXEC dbo.sp_add_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 1,  
        @description = 'Maintenance tasks on catalog application.',  
        @credential_name = 'CatalogApplicationCredential' ;  
    GO  
    -- grants the proxy "Catalog application proxy" access to the ActiveX Scripting subsystem.  
    EXEC dbo.sp_grant_proxy_to_subsystem  
        @proxy_name = N'Catalog application proxy',  
        @subsystem_id = 2 ;  
    GO  
    ```  
  
 <span data-ttu-id="60ff3-147">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="60ff3-147">For more information, see:</span></span>  
  
-   [<span data-ttu-id="60ff3-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60ff3-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="60ff3-149">&#41;&#40;Transact-SQL de sp_add_proxy</span><span class="sxs-lookup"><span data-stu-id="60ff3-149">sp_add_proxy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-proxy-transact-sql)  
  
-   [<span data-ttu-id="60ff3-150">&#41;&#40;Transact-SQL de sp_grant_proxy_to_subsystem</span><span class="sxs-lookup"><span data-stu-id="60ff3-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql)  
  
  
