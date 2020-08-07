---
title: Excluir um proxy do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting SQL Server Agent proxies
- proxies [SQL Server Agent], deleting
- removing SQL Server Agent proxies
ms.assetid: 9248841d-7294-47d4-94f3-b34a0521fabc
author: stevestein
ms.author: sstein
ms.openlocfilehash: a672c6392e2ffed3ca2a7ed655b806d9d093b10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576114"
---
# <a name="delete-a-sql-server-agent-proxy"></a><span data-ttu-id="f2607-102">Delete a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="f2607-102">Delete a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="f2607-103">Este tópico descreve como excluir uma conta proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2607-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f2607-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f2607-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f2607-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="f2607-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f2607-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f2607-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f2607-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="f2607-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f2607-108">**Para excluir uma conta proxy do SQL Server Agent, usando:**</span><span class="sxs-lookup"><span data-stu-id="f2607-108">**To delete a SQL Server Agent proxy account, using:**</span></span>  
  
     [<span data-ttu-id="f2607-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2607-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f2607-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2607-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f2607-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f2607-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f2607-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f2607-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f2607-113">Ao excluir uma conta proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, certifique-se de que o proxy não faça referência a nenhuma etapa de trabalho ativa.</span><span class="sxs-lookup"><span data-stu-id="f2607-113">When you delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account, make sure the proxy does not reference any active job steps.</span></span> <span data-ttu-id="f2607-114">Para verificar se há etapas de trabalho que fazem referência ao proxy, clique com o botão direito do mouse no proxy, selecione **Propriedades**e, em seguida, na caixa de diálogo _proxy_name_**Propriedades da Conta Proxy** , selecione a página **Referências** .</span><span class="sxs-lookup"><span data-stu-id="f2607-114">To check for any job steps that reference the proxy, right-click the proxy, select **Properties**, and then, in the _proxy_name_**Proxy Account Properties** dialog box, select the **References** page.</span></span> <span data-ttu-id="f2607-115">Se excluir um proxy, você terá a opção de reatribuir todas as etapas de trabalho que o utilizam, na caixa de diálogo **Excluir Objeto** .</span><span class="sxs-lookup"><span data-stu-id="f2607-115">If you delete a proxy, you are given the option to reassign all job steps that use that proxy in the **Delete Object** dialog box.</span></span>  
  
-   <span data-ttu-id="f2607-116">Os proxies do[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent usam credenciais para armazenar informações sobre as contas de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="f2607-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="f2607-117">O usuário especificado na credencial deve ter a permissão "Fazer logon como trabalho em lotes" no computador que executa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2607-117">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f2607-118">Agent verifica o acesso a subsistemas de um proxy e fornece acesso ao proxy sempre que a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="f2607-118">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="f2607-119">Se o proxy já não tiver acesso ao subsistema, a etapa de trabalho falhará.</span><span class="sxs-lookup"><span data-stu-id="f2607-119">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="f2607-120">Caso contrário, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent representará o usuário especificado no proxy e executará a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2607-120">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="f2607-121">Se o logon do usuário tiver acesso ao proxy ou se o usuário pertencer a alguma função com acesso ao proxy, ele poderá utilizá-lo em uma etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2607-121">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f2607-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="f2607-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f2607-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="f2607-123">Permissions</span></span>  
 <span data-ttu-id="f2607-124">Somente membros da função de servidor fixa **sysadmin** podem criar, modificar ou excluir contas proxy.</span><span class="sxs-lookup"><span data-stu-id="f2607-124">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f2607-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2607-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="f2607-126">Para excluir uma conta proxy do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f2607-126">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="f2607-127">No **Pesquisador de Objetos**, clique no sinal de adição para expandir um servidor que contém a conta proxy que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="f2607-127">In **Object Explorer**, click the plus sign to expand a server that contains the proxy account that you want to delete.</span></span>  
  
2.  <span data-ttu-id="f2607-128">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="f2607-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f2607-129">Clique no sinal de adição para expandir a pasta **Proxies** .</span><span class="sxs-lookup"><span data-stu-id="f2607-129">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="f2607-130">Clique no sinal de adição para expandir o subsistema que contém a conta proxy que você deseja excluir (por exemplo, **Script ActiveX)**.</span><span class="sxs-lookup"><span data-stu-id="f2607-130">Click the plus sign to expand the subsystem that contains the proxy account you want to delete (for example, **ActiveX Script)**.</span></span>  
  
5.  <span data-ttu-id="f2607-131">Clique com o botão direito do mouse na conta proxy que deseja excluir e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f2607-131">Right-click the proxy account that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="f2607-132">Na caixa de diálogo **Excluir Objeto** , verifique se a conta proxy correta está selecionada.</span><span class="sxs-lookup"><span data-stu-id="f2607-132">In the **Delete Object** dialog box, confirm that the correct proxy account is selected.</span></span> <span data-ttu-id="f2607-133">Marque a caixa de seleção **Reassign to** para reatribuir as etapas de trabalho que fazem referência dessa conta proxy para outra conta.</span><span class="sxs-lookup"><span data-stu-id="f2607-133">Check the **Reassign to** check box to reassign the job steps that reference this proxy account to another account.</span></span>  
  
7.  <span data-ttu-id="f2607-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2607-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f2607-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2607-135">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="f2607-136">Para excluir uma conta proxy do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f2607-136">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="f2607-137">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2607-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f2607-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f2607-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f2607-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f2607-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the proxy "Catalog application proxy"  
    USE msdb ;  
    GO  
    EXEC dbo.sp_delete_proxy  
        @proxy_name = N'Catalog application proxy' ;  
    GO  
    ```  
  
 <span data-ttu-id="f2607-140">Para obter mais informações, consulte [sp_delete_proxy &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f2607-140">For more information, see [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span></span>  
  
  
