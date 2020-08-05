---
title: Modificar um Proxy do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], modifying
- modifying SQL Server Agent proxy
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f86793a8ddcc6fe8f981d6b367d2178c5a794ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572344"
---
# <a name="modify-a-sql-server-agent-proxy"></a><span data-ttu-id="2eb72-102">Modify a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="2eb72-102">Modify a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="2eb72-103">Este tópico descreve como modificar um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proxy do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2eb72-103">This topic describes how to modify a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2eb72-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="2eb72-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2eb72-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2eb72-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2eb72-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="2eb72-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2eb72-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="2eb72-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2eb72-108">**Para modificar um proxy do SQL Server Agent usando:**</span><span class="sxs-lookup"><span data-stu-id="2eb72-108">**To modify a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="2eb72-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2eb72-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2eb72-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2eb72-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2eb72-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2eb72-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2eb72-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="2eb72-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2eb72-113">Os proxies do[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent usam credenciais para armazenar informações sobre as contas de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="2eb72-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="2eb72-114">O usuário especificado na credencial deve ter a permissão "Fazer logon como trabalho em lotes" no computador que executa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2eb72-114">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2eb72-115">Agent verifica o acesso a subsistemas de um proxy e fornece acesso ao proxy sempre que a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="2eb72-115">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="2eb72-116">Se o proxy já não tiver acesso ao subsistema, a etapa de trabalho falhará.</span><span class="sxs-lookup"><span data-stu-id="2eb72-116">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="2eb72-117">Caso contrário, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent representará o usuário especificado no proxy e executará a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2eb72-117">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="2eb72-118">Se o logon do usuário tiver acesso ao proxy ou se o usuário pertencer a alguma função com acesso ao proxy, ele poderá utilizá-lo em uma etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2eb72-118">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2eb72-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="2eb72-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2eb72-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="2eb72-120">Permissions</span></span>  
 <span data-ttu-id="2eb72-121">Somente membros da função de servidor fixa **sysadmin** podem criar, modificar ou excluir contas proxy.</span><span class="sxs-lookup"><span data-stu-id="2eb72-121">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2eb72-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2eb72-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="2eb72-123">Para modificar um proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="2eb72-123">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="2eb72-124">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém a conta proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="2eb72-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account that you want to modify.</span></span>  
  
2.  <span data-ttu-id="2eb72-125">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="2eb72-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="2eb72-126">Clique no sinal de adição para expandir a pasta **Proxies** .</span><span class="sxs-lookup"><span data-stu-id="2eb72-126">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="2eb72-127">Clique no sinal de adição para expandir o nó do subsistema do proxy (por exemplo, **Script do ActiveX**).</span><span class="sxs-lookup"><span data-stu-id="2eb72-127">Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).</span></span>  
  
5.  <span data-ttu-id="2eb72-128">Clique com o botão direito do mouse na conta proxy cujas propriedades serão modificadas e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2eb72-128">Right-click the proxy account you want to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="2eb72-129">Na caixa de diálogo**Propriedades da conta proxy** _proxy_name_, faça alterações na conta proxy, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2eb72-129">In the _proxy_name_**Proxy Account Properties** dialog box, make changes to the proxy account as necessary.</span></span> <span data-ttu-id="2eb72-130">Para obter mais informações sobre as opções dessa caixa de diálogo, consulte [Criar um proxy do SQL Server Agent](create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="2eb72-130">For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md).</span></span>  
  
7.  <span data-ttu-id="2eb72-131">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2eb72-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2eb72-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2eb72-132">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="2eb72-133">Para modificar um proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="2eb72-133">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="2eb72-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb72-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2eb72-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2eb72-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2eb72-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2eb72-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="2eb72-137">Para obter mais informações, consulte [sp_update_proxy &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2eb72-137">For more information, see [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span></span>  
  
  
