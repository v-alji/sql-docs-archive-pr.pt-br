---
title: Configurar a opção de configuração de servidor cost threshold for parallelism | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cost threshold for parallelism option
ms.assetid: dad21bee-fe28-41f6-9d2f-e6ababfaf9db
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 675055a753e84ace3a4fcb44b41b8c914326c5c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570247"
---
# <a name="configure-the-cost-threshold-for-parallelism-server-configuration-option"></a><span data-ttu-id="6fa28-102">Configurar a opção cost threshold for parallelism de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="6fa28-102">Configure the cost threshold for parallelism Server Configuration Option</span></span>
  <span data-ttu-id="6fa28-103">Este tópico descreve como configurar a opção de configuração de servidor **cost threshold for parallelism** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fa28-103">This topic describes how to configure the **cost threshold for parallelism** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6fa28-104">A opção **cost threshold for parallelism** especifica o limite no qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cria e executa planos paralelos para consultas.</span><span class="sxs-lookup"><span data-stu-id="6fa28-104">The **cost threshold for parallelism** option specifies the threshold at which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates and runs parallel plans for queries.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6fa28-105">cria e executa um plano paralelo para uma consulta somente quando o custo estimado para executar um plano serial para a mesma consulta é mais alto que o valor definido em **cost threshold for parallelism**.</span><span class="sxs-lookup"><span data-stu-id="6fa28-105">creates and runs a parallel plan for a query only when the estimated cost to run a serial plan for the same query is higher than the value set in **cost threshold for parallelism**.</span></span> <span data-ttu-id="6fa28-106">O custo faz referência a um tempo decorrido estimado em segundos, exigido para a execução do plano serial em uma configuração de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="6fa28-106">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="6fa28-107">A opção **cost threshold for parallelism** pode ser definida como qualquer valor de 0 a 32767.</span><span class="sxs-lookup"><span data-stu-id="6fa28-107">The **cost threshold for parallelism** option can be set to any value from 0 through 32767.</span></span> <span data-ttu-id="6fa28-108">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="6fa28-108">The default value is 5.</span></span>  
  
 <span data-ttu-id="6fa28-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="6fa28-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6fa28-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6fa28-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6fa28-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6fa28-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6fa28-112">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6fa28-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="6fa28-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="6fa28-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6fa28-114">**Para configurar a opção cost threshold for parallelism, usando:**</span><span class="sxs-lookup"><span data-stu-id="6fa28-114">**To configure the cost threshold for parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="6fa28-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6fa28-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6fa28-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6fa28-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="6fa28-117">**Acompanhamento:**  [depois de configurar a opção cost threshold for parallelism](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="6fa28-117">**Follow Up:**  [After you configure the cost threshold for parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6fa28-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6fa28-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6fa28-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6fa28-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6fa28-120">O custo faz referência a um tempo decorrido estimado em segundos, exigido para a execução do plano serial em uma configuração de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="6fa28-120">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="6fa28-121">Defina apenas **cost threshold for parallelism** em multiprocessadores simétricos.</span><span class="sxs-lookup"><span data-stu-id="6fa28-121">Only set **cost threshold for parallelism** on symmetric multiprocessors.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6fa28-122">ignora o valor do **cost threshold for parallelism** nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="6fa28-122">ignores the **cost threshold for parallelism** value under the following conditions:</span></span>  
  
    -   <span data-ttu-id="6fa28-123">Seu computador só tem um processador lógico.</span><span class="sxs-lookup"><span data-stu-id="6fa28-123">Your computer has only one logical processor.</span></span>  
  
    -   <span data-ttu-id="6fa28-124">Só um único processador lógico está disponível para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devido à opção de configuração **máscara de afinidade** .</span><span class="sxs-lookup"><span data-stu-id="6fa28-124">Only a single logical processor is available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because of the **affinity mask** configuration option.</span></span>  
  
    -   <span data-ttu-id="6fa28-125">A opção **max degree of parallelism** está definida como 1.</span><span class="sxs-lookup"><span data-stu-id="6fa28-125">The **max degree of parallelism** option is set to 1.</span></span>  
  
 <span data-ttu-id="6fa28-126">Um processador lógico é a unidade básica de hardware de processador que permite que o sistema operacional despache uma tarefa ou execute um contexto de thread.</span><span class="sxs-lookup"><span data-stu-id="6fa28-126">A logical processor is the basic unit of processor hardware that allows the operating system to dispatch a task or execute a thread context.</span></span> <span data-ttu-id="6fa28-127">Cada processador lógico pode executar somente um contexto de thread de cada vez.</span><span class="sxs-lookup"><span data-stu-id="6fa28-127">Each logical processor can execute only one thread context at a time.</span></span> <span data-ttu-id="6fa28-128">O núcleo do processador é o circuito que fornece capacidade para decodificar e executar instruções.</span><span class="sxs-lookup"><span data-stu-id="6fa28-128">The processor core is the circuitry that provides ability to decode and execute instructions.</span></span> <span data-ttu-id="6fa28-129">O núcleo de um processador pode conter um ou mais processadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="6fa28-129">A processor core may contain one or more logical processors.</span></span> <span data-ttu-id="6fa28-130">A consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir pode ser usada para obter informações de CPU para o sistema.</span><span class="sxs-lookup"><span data-stu-id="6fa28-130">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] query can be used for obtaining CPU information for the system.</span></span>  
  
```  
SELECT (cpu_count / hyperthread_ratio) AS PhysicalCPUs,   
cpu_count AS logicalCPUs   
FROM sys.dm_os_sys_info  
```  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6fa28-131">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6fa28-131">Recommendations</span></span>  
  
-   <span data-ttu-id="6fa28-132">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fa28-132">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="6fa28-133">Em certos casos, pode ser escolhido um plano paralelo, embora o plano de custo da consulta seja menor do que o valor atual do **cost threshold for parallelism** .</span><span class="sxs-lookup"><span data-stu-id="6fa28-133">In certain cases, a parallel plan may be chosen even though the query's cost plan is less than the current **cost threshold for parallelism** value.</span></span> <span data-ttu-id="6fa28-134">Isso pode acontecer pois a decisão de usar um plano paralelo ou serial tem base em uma estimativa de custo fornecida antes que a otimização completa seja concluída</span><span class="sxs-lookup"><span data-stu-id="6fa28-134">This can happen because the decision to use a parallel or serial plan is based on a cost estimate provided before the full optimization is complete.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6fa28-135">Segurança</span><span class="sxs-lookup"><span data-stu-id="6fa28-135">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6fa28-136">Permissões</span><span class="sxs-lookup"><span data-stu-id="6fa28-136">Permissions</span></span>  
 <span data-ttu-id="6fa28-137">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="6fa28-137">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="6fa28-138">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="6fa28-138">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="6fa28-139">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="6fa28-139">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6fa28-140">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6fa28-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="6fa28-141">Para configurar a opção cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="6fa28-141">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="6fa28-142">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6fa28-142">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="6fa28-143">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="6fa28-143">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="6fa28-144">Em **Paralelismo**, altere a opção **CostThresholdForParallelism** para o valor desejado.</span><span class="sxs-lookup"><span data-stu-id="6fa28-144">Under **Parallelism**, change the **CostThresholdForParallelism** option to the value you want.</span></span> <span data-ttu-id="6fa28-145">Digite ou selecione um valor de 0 a 32767.</span><span class="sxs-lookup"><span data-stu-id="6fa28-145">Type or select a value from 0 to 32767.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6fa28-146">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6fa28-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="6fa28-147">Para configurar a opção cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="6fa28-147">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="6fa28-148">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fa28-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6fa28-149">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6fa28-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6fa28-150">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6fa28-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6fa28-151">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `cost threshold for parallelism` como `10`.</span><span class="sxs-lookup"><span data-stu-id="6fa28-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `cost threshold for parallelism` option to `10`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cost threshold for parallelism', 10 ;  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="6fa28-152">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6fa28-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cost-threshold-for-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="6fa28-153">Acompanhamento: depois de configurar a opção cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="6fa28-153">Follow Up: After you configure the cost threshold for parallelism option</span></span>  
 <span data-ttu-id="6fa28-154">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="6fa28-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa28-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6fa28-155">See Also</span></span>  
 <span data-ttu-id="6fa28-156">[Configurar operações de índice paralelo](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="6fa28-156">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="6fa28-157">[Dicas de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="6fa28-157">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 <span data-ttu-id="6fa28-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6fa28-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="6fa28-159">[Opção affinity mask de configuração de servidor](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="6fa28-159">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="6fa28-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6fa28-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="6fa28-161">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6fa28-161">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="6fa28-162">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6fa28-162">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
