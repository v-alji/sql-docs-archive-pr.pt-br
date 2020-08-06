---
title: Configurar a opção de configuração de servidor max degree of parallelism | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parallel queries [SQL Server]
- processors [SQL Server], parallel queries
- number of processors for parallel queries
- max degree of parallelism option
ms.assetid: 86b65bf1-a6a1-4670-afc0-cdfad1558032
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 824dc837142acc4a0898cb04b4a8687bc5be4043
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575349"
---
# <a name="configure-the-max-degree-of-parallelism-server-configuration-option"></a><span data-ttu-id="db77d-102">Configurar a opção de configuração de servidor max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="db77d-102">Configure the max degree of parallelism Server Configuration Option</span></span>
  <span data-ttu-id="db77d-103">Este tópico descreve como configurar a `max degree of parallelism` opção de configuração de servidor no usando o ou o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db77d-103">This topic describes how to configure the `max degree of parallelism` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="db77d-104">Quando uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é executada em um computador com mais de um microprocessador ou CPU, ele detecta o melhor grau de paralelismo, ou seja, o número de processadores utilizados para executar uma única instrução, para cada execução paralela de plano.</span><span class="sxs-lookup"><span data-stu-id="db77d-104">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on a computer that has more than one microprocessor or CPU, it detects the best degree of parallelism, that is, the number of processors employed to run a single statement, for each parallel plan execution.</span></span> <span data-ttu-id="db77d-105">É possível usar a opção `max degree of parallelism` para limitar o número de processadores a serem usados na execução paralela do plano.</span><span class="sxs-lookup"><span data-stu-id="db77d-105">You can use the `max degree of parallelism` option to limit the number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="db77d-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] considera os planos de execução paralela para consultas, operações DDL (linguagem de definição de dados) e população de cursor estático e controlado por conjunto de chaves.</span><span class="sxs-lookup"><span data-stu-id="db77d-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] considers parallel execution plans for queries, index data definition language (DDL) operations, and static and keyset-driven cursor population.</span></span>  
  
 <span data-ttu-id="db77d-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="db77d-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="db77d-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="db77d-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="db77d-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="db77d-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="db77d-110">Recomendações</span><span class="sxs-lookup"><span data-stu-id="db77d-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="db77d-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="db77d-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="db77d-112">**Para configurar a opção max degree of parallelism usando**</span><span class="sxs-lookup"><span data-stu-id="db77d-112">**To configure the max degree of parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="db77d-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db77d-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="db77d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="db77d-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="db77d-115">**Acompanhamento:**  [depois de configurar a opção max degree of parallelism](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="db77d-115">**Follow Up:**  [After you configure the max degree of parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="db77d-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="db77d-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="db77d-117">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="db77d-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="db77d-118">Se a opção de máscara de afinidade não estiver definida com o padrão, poderá restringir o número de processadores disponíveis para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em sistemas SMP simétricos.</span><span class="sxs-lookup"><span data-stu-id="db77d-118">If the affinity mask option is not set to the default, it may restrict the number of processors available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on symmetric multiprocessing (SMP) systems.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="db77d-119">Recomendações</span><span class="sxs-lookup"><span data-stu-id="db77d-119">Recommendations</span></span>  
  
-   <span data-ttu-id="db77d-120">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db77d-120">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="db77d-121">Para permitir que o servidor determine o grau máximo de paralelismo, defina essa opção como 0, o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="db77d-121">To enable the server to determine the maximum degree of parallelism, set this option to 0, the default value.</span></span> <span data-ttu-id="db77d-122">A definição do grau máximo de paralelismo como 0 permite que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use todos os processadores disponíveis, até 64 processadores.</span><span class="sxs-lookup"><span data-stu-id="db77d-122">Setting maximum degree of parallelism to 0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use all the available processors up to 64 processors.</span></span> <span data-ttu-id="db77d-123">Para suprimir a geração de planos paralelos, defina `max degree of parallelism` como 1.</span><span class="sxs-lookup"><span data-stu-id="db77d-123">To suppress parallel plan generation, set `max degree of parallelism` to 1.</span></span> <span data-ttu-id="db77d-124">Defina o valor como um número de 1 a 32.767 para especificar o número máximo de núcleos de processador que podem ser usados por uma única execução de consulta.</span><span class="sxs-lookup"><span data-stu-id="db77d-124">Set the value to a number from 1 to 32,767 to specify the maximum number of processor cores that can be used by a single query execution.</span></span> <span data-ttu-id="db77d-125">Se um valor maior do que o número de processadores disponíveis for especificado, o número real de processadores disponíveis será usado.</span><span class="sxs-lookup"><span data-stu-id="db77d-125">If a value greater than the number of available processors is specified, the actual number of available processors is used.</span></span> <span data-ttu-id="db77d-126">Se o computador tiver apenas um processador, o valor de `max degree of parallelism` será ignorado.</span><span class="sxs-lookup"><span data-stu-id="db77d-126">If the computer has only one processor, the `max degree of parallelism` value is ignored.</span></span>  
  
-   <span data-ttu-id="db77d-127">Você pode substituir o valor max degree of parallelism nas consultas ao especificar a dica de consulta MAXDOP na instrução de consulta.</span><span class="sxs-lookup"><span data-stu-id="db77d-127">You can override the max degree of parallelism value in queries by specifying the MAXDOP query hint in the query statement.</span></span> <span data-ttu-id="db77d-128">Para obter mais informações, veja [Dicas de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="db77d-128">For more information, see [Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
-   <span data-ttu-id="db77d-129">As operações de índice que criam ou reconstroem um índice ou descartam um índice clusterizado podem usar muitos recursos.</span><span class="sxs-lookup"><span data-stu-id="db77d-129">Index operations that create or rebuild an index, or that drop a clustered index, can be resource intensive.</span></span> <span data-ttu-id="db77d-130">Você pode substituir o valor max degree of parallelism das operações de índice especificando a opção de índice MAXDOP na instrução de índice.</span><span class="sxs-lookup"><span data-stu-id="db77d-130">You can override the max degree of parallelism value for index operations by specifying the MAXDOP index option in the index statement.</span></span> <span data-ttu-id="db77d-131">O valor MAXDOP é aplicado à instrução no tempo de execução e não é armazenado nos metadados do índice.</span><span class="sxs-lookup"><span data-stu-id="db77d-131">The MAXDOP value is applied to the statement at execution time and is not stored in the index metadata.</span></span> <span data-ttu-id="db77d-132">Para obter mais informações, consulte [Configurar operações de índice paralelo](../../relational-databases/indexes/configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="db77d-132">For more information, see [Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md).</span></span>  
  
-   <span data-ttu-id="db77d-133">Além das consultas e das operações de índice, essa opção também controla o paralelismo de DBCC CHECKTABLE, DBCC CHECKDB e DBCC CHECKFILEGROUP.</span><span class="sxs-lookup"><span data-stu-id="db77d-133">In addition to queries and index operations, this option also controls the parallelism of DBCC CHECKTABLE, DBCC CHECKDB, and DBCC CHECKFILEGROUP.</span></span> <span data-ttu-id="db77d-134">É possível desabilitar a execução paralela de planos para essas instruções usando o sinalizador de rastreamento 2528.</span><span class="sxs-lookup"><span data-stu-id="db77d-134">You can disable parallel execution plans for these statements by using trace flag 2528.</span></span> <span data-ttu-id="db77d-135">Para obter mais informações, veja, [Sinalizadores de rastreamento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db77d-135">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="db77d-136">Segurança</span><span class="sxs-lookup"><span data-stu-id="db77d-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="db77d-137">Permissões</span><span class="sxs-lookup"><span data-stu-id="db77d-137">Permissions</span></span>  
 <span data-ttu-id="db77d-138">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="db77d-138">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="db77d-139">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="db77d-139">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="db77d-140">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="db77d-140">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="db77d-141">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db77d-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="db77d-142">Para configurar a opção max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="db77d-142">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="db77d-143">No **Pesquisador de Objetos**, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="db77d-143">In **Object Explorer**, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="db77d-144">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="db77d-144">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="db77d-145">Na caixa **Grau Máximo de Paralelismo** , selecione o número máximo de processadores a serem usados na execução de plano paralelo.</span><span class="sxs-lookup"><span data-stu-id="db77d-145">In the **Max Degree of Parallelism** box, select the maximum number of processors to use in parallel plan execution.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="db77d-146">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="db77d-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="db77d-147">Para configurar a opção max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="db77d-147">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="db77d-148">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db77d-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="db77d-149">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="db77d-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="db77d-150">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="db77d-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="db77d-151">Este exemplo mostra como usar o [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar a opção `max degree of parallelism` como `8`.</span><span class="sxs-lookup"><span data-stu-id="db77d-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max degree of parallelism` option to `8`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO   
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
EXEC sp_configure 'max degree of parallelism', 8;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
```  
  
 <span data-ttu-id="db77d-152">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="db77d-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-degree-of-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="db77d-153">Acompanhamento: depois de configurar a opção grau máximo de paralelismo</span><span class="sxs-lookup"><span data-stu-id="db77d-153">Follow Up: After you configure the max degree of parallelism option</span></span>  
 <span data-ttu-id="db77d-154">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="db77d-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db77d-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db77d-155">See Also</span></span>  
 <span data-ttu-id="db77d-156">[Opção affinity mask de configuração de servidor](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="db77d-156">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="db77d-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="db77d-158">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="db77d-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="db77d-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="db77d-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="db77d-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="db77d-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="db77d-163">[DBCC CHECKtable &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span></span>  
 <span data-ttu-id="db77d-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="db77d-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db77d-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="db77d-166">[Configurar operações de índice paralelo](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="db77d-166">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="db77d-167">[Dicas de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="db77d-167">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="db77d-168">Definir opções de índice</span><span class="sxs-lookup"><span data-stu-id="db77d-168">Set Index Options</span></span>](../../relational-databases/indexes/set-index-options.md)  
  
  
