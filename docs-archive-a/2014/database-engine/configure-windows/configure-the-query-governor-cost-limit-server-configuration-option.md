---
title: Configurar a opção de configuração de servidor query governor cost limit | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], time to execute
- query governor cost limit option [SQL Server]
- time [SQL Server], query run time
ms.assetid: e7b8f084-1052-4133-959b-cebf4add790f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4f8420bf8ed8c08d3626c797968c041a40f7c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570242"
---
# <a name="configure-the-query-governor-cost-limit-server-configuration-option"></a><span data-ttu-id="e7565-102">Configurar a opção query governor cost limit de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="e7565-102">Configure the query governor cost limit Server Configuration Option</span></span>
  <span data-ttu-id="e7565-103">Este tópico descreve como configurar a `query governor cost limit` opção de configuração de servidor no usando o ou o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7565-103">This topic describes how to configure the `query governor cost limit` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e7565-104">A opção query governor cost limit especifica um limite máximo no intervalo de tempo durante o qual poderá ser executada uma consulta.</span><span class="sxs-lookup"><span data-stu-id="e7565-104">The query governor cost limit option specifies an upper limit on the time period in which a query can run.</span></span> <span data-ttu-id="e7565-105">Custo da consulta se refere a um tempo decorrido estimado, em segundos, que é exigido para concluir uma consulta em uma configuração de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="e7565-105">Query cost refers to the estimated elapsed time, in seconds, that is required to complete a query on a specific hardware configuration.</span></span> <span data-ttu-id="e7565-106">O valor padrão para esta opção é 0, que define o administrador de consultas como desativado.</span><span class="sxs-lookup"><span data-stu-id="e7565-106">The default value for this option is 0, which sets the query governor to off.</span></span> <span data-ttu-id="e7565-107">Isso permite que todas as consultas sejam executadas sem limite de tempo.</span><span class="sxs-lookup"><span data-stu-id="e7565-107">This allows all queries to run without any time limitation.</span></span> <span data-ttu-id="e7565-108">Se você especificar um valor que não seja zero nem negativo, o administrador de consultas proibirá a execução de qualquer consulta com um custo estimado que exceda esse valor.</span><span class="sxs-lookup"><span data-stu-id="e7565-108">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost that exceeds that value.</span></span>  
  
 <span data-ttu-id="e7565-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="e7565-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e7565-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e7565-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e7565-111">Recomendações</span><span class="sxs-lookup"><span data-stu-id="e7565-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e7565-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="e7565-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e7565-113">**Para configurar a opção query governor cost limit, usando:**</span><span class="sxs-lookup"><span data-stu-id="e7565-113">**To configure the query governor cost limit option, using:**</span></span>  
  
     [<span data-ttu-id="e7565-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7565-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e7565-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7565-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="e7565-116">**Acompanhamento:**  [depois de configurar a opção query governor cost limit](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="e7565-116">**Follow Up:**  [After you configure the query governor cost limit option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7565-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e7565-117">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e7565-118">Recomendações</span><span class="sxs-lookup"><span data-stu-id="e7565-118">Recommendations</span></span>  
  
-   <span data-ttu-id="e7565-119">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7565-119">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="e7565-120">Para alterar o valor de query governor cost limit com base na conexão, use a instrução [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e7565-120">To change the value query governor cost limit on a per-connection basis, use the [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7565-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="e7565-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7565-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="e7565-122">Permissions</span></span>  
 <span data-ttu-id="e7565-123">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="e7565-123">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="e7565-124">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="e7565-124">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="e7565-125">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="e7565-125">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e7565-126">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7565-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="e7565-127">Para configurar a opção query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="e7565-127">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="e7565-128">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e7565-128">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="e7565-129">Clique na página **Conexões** .</span><span class="sxs-lookup"><span data-stu-id="e7565-129">Click the **Connections** page.</span></span>  
  
3.  <span data-ttu-id="e7565-130">Marque ou desmarque a caixa de seleção **Usar administrador de consultas para evitar consultas demoradas** .</span><span class="sxs-lookup"><span data-stu-id="e7565-130">Select or clear the **Use query governor to prevent long-running queries** check box.</span></span>  
  
     <span data-ttu-id="e7565-131">Se você marcar essa caixa de seleção, na caixa abaixo, insira um valor positivo a ser usado pelo administrador de consultas para impedir a execução de qualquer consulta com um tempo de execução além desse valor.</span><span class="sxs-lookup"><span data-stu-id="e7565-131">If you select this check box, in the box below, enter a positive value, which the query governor uses to disallow execution of any query with a running length exceeding that value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e7565-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7565-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="e7565-133">Para configurar a opção query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="e7565-133">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="e7565-134">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7565-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7565-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e7565-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7565-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e7565-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7565-137">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `query governor cost limit` como `120` segundos.</span><span class="sxs-lookup"><span data-stu-id="e7565-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query governor cost limit` option to `120` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query governor cost limit', 120 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="e7565-138">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e7565-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-governor-cost-limit-option"></a><a name="FollowUp"></a> <span data-ttu-id="e7565-139">Acompanhamento: depois de configurar a opção query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="e7565-139">Follow Up: After you configure the query governor cost limit option</span></span>  
 <span data-ttu-id="e7565-140">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="e7565-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7565-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7565-141">See Also</span></span>  
 <span data-ttu-id="e7565-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7565-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="e7565-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7565-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span></span>  
 <span data-ttu-id="e7565-144">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e7565-144">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="e7565-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7565-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
