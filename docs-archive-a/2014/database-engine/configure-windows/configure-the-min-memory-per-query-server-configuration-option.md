---
title: Configurar a opção de configuração de servidor min memory per query | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- memory [SQL Server], queries
- minimum query memory
- queries [SQL Server], memory
- min memory per query option
ms.assetid: ecd3fb79-b4a6-432f-9ef5-530e0d42d5a6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 56d85f36840f0900c8b5e986334a99ba610d3930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575341"
---
# <a name="configure-the-min-memory-per-query-server-configuration-option"></a><span data-ttu-id="64053-102">Configurar a opção min memory per query de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="64053-102">Configure the min memory per query Server Configuration Option</span></span>
  <span data-ttu-id="64053-103">Este tópico descreve como configurar a `min memory per query` opção de configuração de servidor no usando o ou o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64053-103">This topic describes how to configure the `min memory per query` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="64053-104">A `min memory per query` opção especifica a quantidade mínima de memória (em quilobytes) que será alocada para a execução de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="64053-104">The `min memory per query` option specifies the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span> <span data-ttu-id="64053-105">Por exemplo, se `min memory per query` for definido como 2.048 KB, a consulta será garantida para obter pelo menos essa quantidade total de memória.</span><span class="sxs-lookup"><span data-stu-id="64053-105">For example, if `min memory per query` is set to 2,048 KB, the query is guaranteed to get at least that much total memory.</span></span> <span data-ttu-id="64053-106">O valor padrão é 1.024 KB.</span><span class="sxs-lookup"><span data-stu-id="64053-106">The default value is 1,024 KB.</span></span> <span data-ttu-id="64053-107">O valor mínimo é de 512 KB e o valor máximo é 2.147.483.647 KB (2 GB).</span><span class="sxs-lookup"><span data-stu-id="64053-107">The minimum value 512 KB, and the maximum is 2,147,483,647 KB (2 GB).</span></span>  
  
 <span data-ttu-id="64053-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="64053-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="64053-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="64053-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="64053-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="64053-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="64053-111">Recomendações</span><span class="sxs-lookup"><span data-stu-id="64053-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="64053-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="64053-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="64053-113">**Para configurar a opção min memory per query usando:**</span><span class="sxs-lookup"><span data-stu-id="64053-113">**To configure the min memory per query option, using:**</span></span>  
  
     [<span data-ttu-id="64053-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64053-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="64053-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64053-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="64053-116">**Acompanhamento:**  [depois de configurar a opção min memory per query](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="64053-116">**Follow Up:**  [After you configure the min memory per query option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="64053-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="64053-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="64053-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="64053-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="64053-119">A quantidade mínima de memória por consulta tem precedência sobre a [opção index create memory](configure-the-index-create-memory-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="64053-119">The amount of min memory per query has precedence over the [index create memory Option](configure-the-index-create-memory-server-configuration-option.md).</span></span> <span data-ttu-id="64053-120">Quando ambas as opções são modificadas, e a index create memory é inferior à min memory per query, você recebe uma mensagem de aviso, mas o valor é definido.</span><span class="sxs-lookup"><span data-stu-id="64053-120">If you modify both options and the index create memory is less than min memory per query, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="64053-121">Durante a execução da consulta, você receberá um outro aviso semelhante.</span><span class="sxs-lookup"><span data-stu-id="64053-121">During query execution you receive another similar warning.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="64053-122">Recomendações</span><span class="sxs-lookup"><span data-stu-id="64053-122">Recommendations</span></span>  
  
-   <span data-ttu-id="64053-123">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64053-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="64053-124">O processador de consulta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tenta determinar a quantidade ideal de memória a ser alocada para uma consulta.</span><span class="sxs-lookup"><span data-stu-id="64053-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query processor tries to determine the optimal amount of memory to allocate to a query.</span></span> <span data-ttu-id="64053-125">A opção min memory per query deixa o administrador especificar a quantia mínima de memória que qualquer consulta única recebe.</span><span class="sxs-lookup"><span data-stu-id="64053-125">The min memory per query option lets the administrator specify the minimum amount of memory any single query receives.</span></span> <span data-ttu-id="64053-126">As consultas geralmente receberão mais memória que isso, se tiverem operações hash e de classificação em um grande volume de dados.</span><span class="sxs-lookup"><span data-stu-id="64053-126">Queries generally receive more memory than this if they have hash and sort operations on a large volume of data.</span></span> <span data-ttu-id="64053-127">Aumentar o valor de min memory per query pode melhorar o desempenho para algumas consultas de tamanho pequeno a médio, mas fazer isso poderia conduzir a uma maior competição por recursos de memória.</span><span class="sxs-lookup"><span data-stu-id="64053-127">Increasing the value of min memory per query may improve performance for some small to medium-sized queries, but doing so could lead to increased competition for memory resources.</span></span> <span data-ttu-id="64053-128">A opção min memory per query inclui a memória alocada para classificação.</span><span class="sxs-lookup"><span data-stu-id="64053-128">The min memory per query option includes memory allocated for sorting.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64053-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="64053-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64053-130">Permissões</span><span class="sxs-lookup"><span data-stu-id="64053-130">Permissions</span></span>  
 <span data-ttu-id="64053-131">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="64053-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="64053-132">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="64053-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="64053-133">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="64053-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="64053-134">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="64053-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="64053-135">Para configurar a opção min memory per query</span><span class="sxs-lookup"><span data-stu-id="64053-135">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="64053-136">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="64053-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="64053-137">Clique no nó **Memória** .</span><span class="sxs-lookup"><span data-stu-id="64053-137">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="64053-138">Na caixa **Memória mínima por consulta** , insira a quantidade mínima de memória (em quilobytes) que será alocada para a execução de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="64053-138">In the **Minimum memory per query** box, enter the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="64053-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="64053-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="64053-140">Para configurar a opção min memory per query</span><span class="sxs-lookup"><span data-stu-id="64053-140">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="64053-141">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64053-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="64053-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="64053-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="64053-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="64053-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="64053-144">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `min memory per query` como `3500` KB.</span><span class="sxs-lookup"><span data-stu-id="64053-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `min memory per query` option to `3500` KB.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'min memory per query', 3500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-min-memory-per-query-option"></a><a name="FollowUp"></a> <span data-ttu-id="64053-145">Acompanhamento: depois de configurar a opção min memory per query</span><span class="sxs-lookup"><span data-stu-id="64053-145">Follow Up: After you configure the min memory per query option</span></span>  
 <span data-ttu-id="64053-146">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="64053-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64053-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64053-147">See Also</span></span>  
 <span data-ttu-id="64053-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="64053-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="64053-149">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="64053-149">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="64053-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="64053-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="64053-151">Configurar a opção index create memory de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="64053-151">Configure the index create memory Server Configuration Option</span></span>](configure-the-index-create-memory-server-configuration-option.md)  
  
  
