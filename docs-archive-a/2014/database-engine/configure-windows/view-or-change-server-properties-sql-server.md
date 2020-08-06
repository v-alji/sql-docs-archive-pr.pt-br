---
title: Exibir ou alterar propriedades do servidor (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- viewing server properties
- server properties [SQL Server]
- displaying server properties
- servers [SQL Server], viewing
ms.assetid: 55f3ac04-5626-4ad2-96bd-a1f1b079659d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 415d4e2d1aaa3166ae4df2dea53b34e064544e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679511"
---
# <a name="view-or-change-server-properties-sql-server"></a><span data-ttu-id="b90ea-102">Exibir ou alterar propriedades de servidor (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b90ea-102">View or Change Server Properties (SQL Server)</span></span>
  <span data-ttu-id="b90ea-103">Este tópico descreve como exibir ou alterar as propriedades de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]ou SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b90ea-103">This topic describes how to view or change the properties of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Configuration Manager.</span></span>  
  
 <span data-ttu-id="b90ea-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b90ea-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b90ea-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b90ea-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b90ea-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b90ea-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b90ea-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="b90ea-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b90ea-108">**Para exibir ou alterar propriedades de servidor, usando:**</span><span class="sxs-lookup"><span data-stu-id="b90ea-108">**To view or change server properties, using:**</span></span>  
  
     [<span data-ttu-id="b90ea-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b90ea-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b90ea-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b90ea-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b90ea-111">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b90ea-111">SQL Server Configuration Manager</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="b90ea-112">**Acompanhamento:**  [depois que você altera as propriedades de servidor](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b90ea-112">**Follow Up:**  [After you change server properties](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b90ea-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b90ea-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b90ea-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b90ea-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b90ea-115">Ao usar sp_configure, você deve executar RECONFIGURE ou RECONFIGURE WITH OVERRIDE depois de definir uma opção de configuração.</span><span class="sxs-lookup"><span data-stu-id="b90ea-115">When using sp_configure, you must run either RECONFIGURE or RECONFIGURE WITH OVERRIDE after setting a configuration option.</span></span> <span data-ttu-id="b90ea-116">A instrução RECONFIGURE WITH OVERRIDE normalmente é reservada para opções de configuração que devem ser usadas com extrema cautela.</span><span class="sxs-lookup"><span data-stu-id="b90ea-116">The RECONFIGURE WITH OVERRIDE statement is usually reserved for configuration options that should be used with extreme caution.</span></span> <span data-ttu-id="b90ea-117">Entretanto, RECONFIGURE WITH OVERRIDE funciona com todas as opções de configuração e você pode usá-la em vez de RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="b90ea-117">However, RECONFIGURE WITH OVERRIDE works for all configuration options, and you can use it in place of RECONFIGURE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b90ea-118">RECONFIGURE é executada em uma transação.</span><span class="sxs-lookup"><span data-stu-id="b90ea-118">RECONFIGURE executes within a transaction.</span></span> <span data-ttu-id="b90ea-119">Se ocorrer falha de alguma operação de reconfiguração, nenhuma das operações de reconfiguração entrará em vigor.</span><span class="sxs-lookup"><span data-stu-id="b90ea-119">If any of the reconfigure operations fail, none of the reconfigure operations will take effect.</span></span>  
  
-   <span data-ttu-id="b90ea-120">Algumas páginas de propriedades apresentam informações obtidas através da WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="b90ea-120">Some property pages present information obtained via Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="b90ea-121">Para exibir essas páginas, a WMI deve ser instalada no computador que está executando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b90ea-121">To display those pages, WMI must be installed on the computer running [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b90ea-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="b90ea-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b90ea-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="b90ea-123">Permissions</span></span>  
 <span data-ttu-id="b90ea-124">Para obter mais informações, veja [Funções de nível de servidor](../../relational-databases/security/authentication-access/server-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b90ea-124">For more information, see [Server-Level Roles](../../relational-databases/security/authentication-access/server-level-roles.md).</span></span>  
  
 <span data-ttu-id="b90ea-125">As permissões execute no sem `sp_configure` parâmetros ou com apenas o primeiro parâmetro são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="b90ea-125">Execute permissions on `sp_configure` with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="b90ea-126">Para executar `sp_configure` com ambos os parâmetros para alterar uma opção de configuração ou para executar a instrução RECONFIGURE, um usuário deve receber a permissão de nível de servidor ALTER Settings.</span><span class="sxs-lookup"><span data-stu-id="b90ea-126">To execute `sp_configure` with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="b90ea-127">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="b90ea-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b90ea-128">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b90ea-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="b90ea-129">Para exibir ou alterar propriedades de servidor</span><span class="sxs-lookup"><span data-stu-id="b90ea-129">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="b90ea-130">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-130">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b90ea-131">Na caixa de diálogo **Propriedades do Servidor** , clique em uma página para exibir ou alterar informações de servidor sobre ela.</span><span class="sxs-lookup"><span data-stu-id="b90ea-131">In the **Server Properties** dialog box, click a page to view or change server information about that page.</span></span> <span data-ttu-id="b90ea-132">Algumas propriedades são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="b90ea-132">Some properties are read-only.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b90ea-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b90ea-133">Using Transact-SQL</span></span>  
  
#### <a name="to-view-server-properties-by-using-the-serverproperty-built-in-function"></a><span data-ttu-id="b90ea-134">Para exibir propriedades de servidor usando a função interna SERVERPROPERTY</span><span class="sxs-lookup"><span data-stu-id="b90ea-134">To view server properties by using the SERVERPROPERTY built-in function</span></span>  
  
1.  <span data-ttu-id="b90ea-135">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b90ea-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b90ea-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b90ea-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b90ea-138">Este exemplo usa a função [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) em uma função interna em uma instrução `SELECT` para retornar informações sobre o servidor atual.</span><span class="sxs-lookup"><span data-stu-id="b90ea-138">This example uses the [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) built-in function in a `SELECT` statement to return information about the current server.</span></span> <span data-ttu-id="b90ea-139">Essa situação é útil quando existem diversas instâncias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no servidor Windows e o cliente deve abrir outra conexão à mesma instância usada pela conexão atual.</span><span class="sxs-lookup"><span data-stu-id="b90ea-139">This scenario is useful when there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on a Windows-based server, and the client must open another connection to the same instance that is used by the current connection.</span></span>  
  
    ```sql  
    SELECT CONVERT( sysname, SERVERPROPERTY('servername'));  
    GO  
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysservers-catalog-view"></a><span data-ttu-id="b90ea-140">Para exibir propriedades de servidor usando a exibição do catálogo sys.servers</span><span class="sxs-lookup"><span data-stu-id="b90ea-140">To view server properties by using the sys.servers catalog view</span></span>  
  
1.  <span data-ttu-id="b90ea-141">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b90ea-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b90ea-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b90ea-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b90ea-144">Este exemplo consulta a exibição de catálogo [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) para retornar o nome (`name`) e a ID (`server_id`) do servidor atual e o nome do provedor OLE DB (`provider`) para conectar a um servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="b90ea-144">This example queries the [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) catalog view to return the name (`name`) and ID (`server_id`) of the current server, and the name of the OLE DB provider (`provider`) for connecting to a linked server.</span></span>  
  
    ```sql  
    USE AdventureWorks2012;   
    GO  
    SELECT name, server_id, provider  
    FROM sys.servers ;   
    GO
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysconfigurations-catalog-view"></a><span data-ttu-id="b90ea-145">Para exibir propriedades de servidor usando a exibição do catálogo sys.configurations</span><span class="sxs-lookup"><span data-stu-id="b90ea-145">To view server properties by using the sys.configurations catalog view</span></span>  
  
1.  <span data-ttu-id="b90ea-146">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b90ea-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b90ea-147">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b90ea-148">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-148">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b90ea-149">Este exemplo consulta a exibição do catálogo [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) para retornar informações sobre cada opção de configuração de servidor no servidor atual.</span><span class="sxs-lookup"><span data-stu-id="b90ea-149">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to return information about each server configuration option on the current server.</span></span> <span data-ttu-id="b90ea-150">O exemplo retorna o nome (`name`) e a descrição (`description`) da opção e se a opção é uma opção avançada (`is_advanced`).</span><span class="sxs-lookup"><span data-stu-id="b90ea-150">The example returns the name (`name`) and description (`description`) of the option and whether the option is an advanced option (`is_advanced`).</span></span>  
  
    ```sql
    USE AdventureWorks2012;
    GO  
    SELECT name, description, is_advanced  
    FROM sys.configurations ;
    GO
    ```  
  
#### <a name="to-change-a-server-property-by-using-sp_configure"></a><span data-ttu-id="b90ea-151">Para alterar uma propriedade de servidor usando sp_configure</span><span class="sxs-lookup"><span data-stu-id="b90ea-151">To change a server property by using sp_configure</span></span>  
  
1.  <span data-ttu-id="b90ea-152">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b90ea-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b90ea-153">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b90ea-154">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b90ea-155">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para alterar a propriedade de um servidor.</span><span class="sxs-lookup"><span data-stu-id="b90ea-155">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to change a server property.</span></span> <span data-ttu-id="b90ea-156">O exemplo altera o valor da opção `fill factor` para `100`.</span><span class="sxs-lookup"><span data-stu-id="b90ea-156">The example changes the value of the `fill factor` option to `100`.</span></span> <span data-ttu-id="b90ea-157">O servidor deve ser reiniciado para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="b90ea-157">The server must be restarted before the change can take effect.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="b90ea-158">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b90ea-158">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="b90ea-159">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b90ea-159">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="b90ea-160">Algumas propriedades de servidor podem ser exibidas ou alteradas usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b90ea-160">Some server properties can be viewed or changed by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="b90ea-161">Por exemplo, você pode exibir a versão e a edição da instância de SQL Server ou alterar o local onde os arquivos do log de erros estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="b90ea-161">For example, you can view the version and edition of the instance of SQL Server, or change the location where error log files are stored.</span></span> <span data-ttu-id="b90ea-162">Estas propriedades também podem ser exibidas consultando [Funções e exibições de gerenciamento dinâmico relacionadas ao servidor](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b90ea-162">These properties can also be viewed by querying the [Server-Related Dynamic Management Views and Functions](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="b90ea-163">Para exibir ou alterar propriedades de servidor</span><span class="sxs-lookup"><span data-stu-id="b90ea-163">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="b90ea-164">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-164">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="b90ea-165">No **SQL Server Configuration Manager**, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-165">In **SQL Server Configuration Manager**, click **SQL Server Services**.</span></span>  
  
3.  <span data-ttu-id="b90ea-166">No painel detalhes, clique com o botão direito do mouse em **SQL Server (\<***instancename***>)** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-166">In the details pane, right-click **SQL Server (\<***instancename***>)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b90ea-167">No **SQL Server (\<***instancename***>) na caixa de diálogo Propriedades**, altere as propriedades do servidor na guia **Serviço** ou na guia **Avançado** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b90ea-167">In the **SQL Server (\<***instancename***>) Properties** dialog box, change the server properties on the **Service** tab or the **Advanced** tab, and then click **OK**.</span></span>  
  
##  <a name="follow-up-after-you-change-server-properties"></a><a name="FollowUp"></a><span data-ttu-id="b90ea-168">Acompanhamento: depois de alterar as propriedades do servidor</span><span class="sxs-lookup"><span data-stu-id="b90ea-168">Follow Up: After you change server properties</span></span>  
 <span data-ttu-id="b90ea-169">Para algumas propriedades, o servidor terá que ser reiniciado antes de a alteração entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="b90ea-169">For some properties, the server might have to be restarted before the change can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b90ea-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b90ea-170">See Also</span></span>  
 <span data-ttu-id="b90ea-171">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b90ea-171">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b90ea-172">[Instruções SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b90ea-172">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 <span data-ttu-id="b90ea-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b90ea-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="b90ea-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b90ea-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="b90ea-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b90ea-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="b90ea-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b90ea-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="b90ea-177">[Configurar o WMI para mostrar o status do servidor nas Ferramentas do SQL Server](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b90ea-177">[Configure WMI to Show Server Status in SQL Server Tools](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span></span>  
 <span data-ttu-id="b90ea-178">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b90ea-178">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="b90ea-179">[Funções de configuração &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b90ea-179">[Configuration Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span></span>  
 [<span data-ttu-id="b90ea-180">Exibições e funções de gerenciamento dinâmico relacionadas ao servidor &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b90ea-180">Server-Related Dynamic Management Views and Functions &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql)  
