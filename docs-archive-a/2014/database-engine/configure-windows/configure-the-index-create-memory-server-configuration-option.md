---
title: Configurar a opção de configuração de servidor index create memory | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- index create memory option
ms.assetid: 3d722d9b-bada-4bf5-a9d7-bfc556bb4915
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd0aeb93d3fb68089338335068fdaaae19919fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680625"
---
# <a name="configure-the-index-create-memory-server-configuration-option"></a><span data-ttu-id="951cc-102">Configurar a opção de configuração de servidor index create memory</span><span class="sxs-lookup"><span data-stu-id="951cc-102">Configure the index create memory Server Configuration Option</span></span>
  <span data-ttu-id="951cc-103">Este tópico descreve como configurar a opção de configuração de servidor **index create memory** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="951cc-103">This topic describes how to configure the **index create memory** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="951cc-104">A opção **index create memory** controla a quantidade máxima de memória alocada inicialmente para criar índices.</span><span class="sxs-lookup"><span data-stu-id="951cc-104">The **index create memory** option controls the maximum amount of memory initially allocated for creating indexes.</span></span> <span data-ttu-id="951cc-105">O valor padrão dessa opção é 0 (autoconfigurável).</span><span class="sxs-lookup"><span data-stu-id="951cc-105">The default value for this option is 0 (self-configuring).</span></span> <span data-ttu-id="951cc-106">Se mais tarde for preciso mais memória para criação de índice e a memória estiver disponível, o servidor irá usá-la, excedendo assim a configuração dessa opção.</span><span class="sxs-lookup"><span data-stu-id="951cc-106">If more memory is later needed for index creation and the memory is available, the server will use it; thereby, exceeding the setting of this option.</span></span> <span data-ttu-id="951cc-107">Se a memória adicional não estiver disponível, a criação de índice continuará usando a memória já alocada.</span><span class="sxs-lookup"><span data-stu-id="951cc-107">If additional memory is not available, the index creation will continue using the memory already allocated.</span></span>  
  
 <span data-ttu-id="951cc-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="951cc-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="951cc-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="951cc-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="951cc-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="951cc-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="951cc-111">Recomendações</span><span class="sxs-lookup"><span data-stu-id="951cc-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="951cc-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="951cc-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="951cc-113">**Para configurar a opção index create memory usando:**</span><span class="sxs-lookup"><span data-stu-id="951cc-113">**To configure the index create memory option, using:**</span></span>  
  
     [<span data-ttu-id="951cc-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="951cc-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="951cc-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="951cc-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="951cc-116">**Acompanhamento:**  [depois de configurar a opção index create memory](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="951cc-116">**Follow Up:**  [After you configure the index create memory option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="951cc-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="951cc-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="951cc-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="951cc-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="951cc-119">A configuração da opção **min memory per query** tem precedência sobre a opção **index create memory**.</span><span class="sxs-lookup"><span data-stu-id="951cc-119">The setting of the **min memory per query** option has precedence over the **index create memory** option.</span></span> <span data-ttu-id="951cc-120">Quando ambas as opções são alteradas, e a **index create memory** é inferior à **min memory per query**, você recebe uma mensagem de aviso, mas o valor foi definido.</span><span class="sxs-lookup"><span data-stu-id="951cc-120">If you change both options and the **index create memory** is less than **min memory per query**, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="951cc-121">Durante a execução de consulta, você recebe um aviso semelhante.</span><span class="sxs-lookup"><span data-stu-id="951cc-121">During query execution, you receive a similar warning.</span></span>  
  
-   <span data-ttu-id="951cc-122">Ao usar tabelas e índices particionados, os requisitos mínimos de memória para criação de índice podem aumentar significativamente se houver índices particionados não alinhados e um alto grau de paralelismo.</span><span class="sxs-lookup"><span data-stu-id="951cc-122">When using partitioned tables and indexes, the minimum memory requirements for index creation may increase significantly if there are non-aligned partitioned indexes and a high degree of parallelism.</span></span> <span data-ttu-id="951cc-123">Essa opção controla a quantidade inicial total de memória alocada para todas as partições de índice em uma única operação de criação de índice.</span><span class="sxs-lookup"><span data-stu-id="951cc-123">This option controls the total initial amount of memory allocated for all index partitions in a single index creation operation.</span></span> <span data-ttu-id="951cc-124">A consulta terminará com uma mensagem de erro se a quantidade definida por essa opção for inferior ao mínimo exigido para a execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="951cc-124">The query will terminate with an error message if the amount set by this option is less than the minimum required to run the query.</span></span>  
  
-   <span data-ttu-id="951cc-125">O valor de execução para essa opção não excederá a quantidade real de memória que pode ser usada pelo sistema operacional e pela plataforma de hardware nas quais o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="951cc-125">The run value for this option will not exceed the actual amount of memory that can be used for the operating system and hardware platform on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="951cc-126">Em sistemas operacionais de 32 bits, o valor de execução será inferior a 3 GB (gigabytes).</span><span class="sxs-lookup"><span data-stu-id="951cc-126">On 32-bit operating systems, the run value will be less than 3 gigabytes (GB).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="951cc-127">Recomendações</span><span class="sxs-lookup"><span data-stu-id="951cc-127">Recommendations</span></span>  
  
-   <span data-ttu-id="951cc-128">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="951cc-128">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="951cc-129">A opção **memória de criação de índice** é autoconfigurável e, normalmente, opera sem necessidade de ajustes.</span><span class="sxs-lookup"><span data-stu-id="951cc-129">The **index create memory** option is self-configuring and usually works without requiring adjustment.</span></span> <span data-ttu-id="951cc-130">Porém, se você tiver dificuldade para criar índices, considere aumentar o valor dessa opção a partir de seu valor de execução.</span><span class="sxs-lookup"><span data-stu-id="951cc-130">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="951cc-131">Segurança</span><span class="sxs-lookup"><span data-stu-id="951cc-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="951cc-132">Permissões</span><span class="sxs-lookup"><span data-stu-id="951cc-132">Permissions</span></span>  
 <span data-ttu-id="951cc-133">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="951cc-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="951cc-134">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="951cc-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="951cc-135">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="951cc-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="951cc-136">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="951cc-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="951cc-137">Para configurar a opção index create memory</span><span class="sxs-lookup"><span data-stu-id="951cc-137">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="951cc-138">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="951cc-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="951cc-139">Clique no nó **Memória** .</span><span class="sxs-lookup"><span data-stu-id="951cc-139">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="951cc-140">Em **Memória de criação de índice**, digite ou selecione o valor desejado para a opção index create memory.</span><span class="sxs-lookup"><span data-stu-id="951cc-140">Under **Index creation memory**, type or select the desired value for the index create memory option.</span></span>  
  
     <span data-ttu-id="951cc-141">Use a opção **index create memory** para controlar a quantidade de memória usada por classificações de criação de índice.</span><span class="sxs-lookup"><span data-stu-id="951cc-141">Use the **index create memory** option to control the amount of memory used by index creation sorts.</span></span> <span data-ttu-id="951cc-142">A opção **memória de criação de índice** é autoconfigurável e deve funcionar na maioria dos casos sem necessidade de ajustes.</span><span class="sxs-lookup"><span data-stu-id="951cc-142">The **index create memory** option is self-configuring and should work in most cases without requiring adjustment.</span></span> <span data-ttu-id="951cc-143">Porém, se você tiver dificuldade para criar índices, considere aumentar o valor dessa opção a partir de seu valor de execução.</span><span class="sxs-lookup"><span data-stu-id="951cc-143">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span> <span data-ttu-id="951cc-144">Classificações de consulta são controladas pela opção **min memory per query** .</span><span class="sxs-lookup"><span data-stu-id="951cc-144">Query sorts are controlled through the **min memory per query** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="951cc-145">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="951cc-145">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="951cc-146">Para configurar a opção index create memory</span><span class="sxs-lookup"><span data-stu-id="951cc-146">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="951cc-147">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="951cc-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="951cc-148">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="951cc-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="951cc-149">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="951cc-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="951cc-150">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `index create memory` como `4096`.</span><span class="sxs-lookup"><span data-stu-id="951cc-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `index create memory` option to `4096`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
EXEC sp_configure 'index create memory', 4096  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="951cc-151">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="951cc-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-index-create-memory-option"></a><a name="FollowUp"></a> <span data-ttu-id="951cc-152">Acompanhamento: depois de configurar a opção index create memory</span><span class="sxs-lookup"><span data-stu-id="951cc-152">Follow Up: After you configure the index create memory option</span></span>  
 <span data-ttu-id="951cc-153">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="951cc-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951cc-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="951cc-154">See Also</span></span>  
 <span data-ttu-id="951cc-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="951cc-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span></span>  
 <span data-ttu-id="951cc-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="951cc-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="951cc-157">[Opções Server Memory de configuração do servidor](server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="951cc-157">[Server Memory Server Configuration Options](server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="951cc-158">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="951cc-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="951cc-159">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="951cc-159">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
