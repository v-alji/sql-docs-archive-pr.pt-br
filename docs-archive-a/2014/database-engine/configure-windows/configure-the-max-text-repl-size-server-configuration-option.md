---
title: Configurar a opção de configuração de servidor max text repl size | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- max text repl size option
ms.assetid: 3056cf64-621d-4996-9162-3913f6bc6d5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af0cf426583ee328f0a484de1c3539836c0d8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575346"
---
# <a name="configure-the-max-text-repl-size-server-configuration-option"></a><span data-ttu-id="154f8-102">Configurar a opção de configuração de servidor max text repl size</span><span class="sxs-lookup"><span data-stu-id="154f8-102">Configure the max text repl size Server Configuration Option</span></span>
  <span data-ttu-id="154f8-103">Este tópico descreve como configurar a opção de configuração de servidor **max text repl size** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="154f8-103">This topic describes how to configure the **max text repl size** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="154f8-104">A opção **max text repl size** especifica o tamanho máximo (em bytes) de `text` ,,,,, e os `ntext` `varchar(max)` `nvarchar(max)` `varbinary(max)` `xml` `image` dados que podem ser adicionados a uma coluna replicada ou capturada em uma única instrução INSERT, Update, WRITETEXT ou UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="154f8-104">The **max text repl size** option specifies the maximum size (in bytes) of `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, `xml`, and `image` data that can be added to a replicated column or captured column in a single INSERT, UPDATE, WRITETEXT, or UPDATETEXT statement.</span></span> <span data-ttu-id="154f8-105">O valor padrão é 65536 bytes.</span><span class="sxs-lookup"><span data-stu-id="154f8-105">The default value is 65536 bytes.</span></span> <span data-ttu-id="154f8-106">O valor -1 indica que não há limite de tamanho além do limite imposto pelo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="154f8-106">A value of -1 indicates that there is no size limit, other than the limit imposed by the data type.</span></span>  
  
 <span data-ttu-id="154f8-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="154f8-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="154f8-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="154f8-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="154f8-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="154f8-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="154f8-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="154f8-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="154f8-111">**Para configurar a opção max text repl size usando:**</span><span class="sxs-lookup"><span data-stu-id="154f8-111">**To configure the max text repl size option, using:**</span></span>  
  
     [<span data-ttu-id="154f8-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="154f8-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="154f8-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="154f8-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="154f8-114">**Acompanhamento:**  [depois de configurar a opção max text repl size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="154f8-114">**Follow Up:**  [After you configure the max text repl size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="154f8-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="154f8-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="154f8-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="154f8-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="154f8-117">Essa opção se aplica à replicação transacional e ao Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="154f8-117">This option applies to transactional replication and Change Data Capture.</span></span> <span data-ttu-id="154f8-118">Quando um servidor é configurado para replicação transacional e Change Data Capture, o valor especificado se aplica a ambos recursos.</span><span class="sxs-lookup"><span data-stu-id="154f8-118">When a server is configured for both transactional replication and Change Data Capture, the specified value applies to both features.</span></span> <span data-ttu-id="154f8-119">Essa opção é ignorada pela replicação de instantâneo e replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="154f8-119">This option is ignored by snapshot replication and merge replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="154f8-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="154f8-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="154f8-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="154f8-121">Permissions</span></span>  
 <span data-ttu-id="154f8-122">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="154f8-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="154f8-123">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="154f8-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="154f8-124">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="154f8-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="154f8-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="154f8-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="154f8-126">Para configurar a opção max text repl size</span><span class="sxs-lookup"><span data-stu-id="154f8-126">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="154f8-127">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="154f8-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="154f8-128">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="154f8-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="154f8-129">Em **Diversos**, altere a opção **Tamanho Máximo da Replicação de Texto** para o valor desejado.</span><span class="sxs-lookup"><span data-stu-id="154f8-129">Under **Miscellaneous**, change the **Max Text Replication Size** option to the desired value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="154f8-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="154f8-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="154f8-131">Para configurar a opção max text repl size</span><span class="sxs-lookup"><span data-stu-id="154f8-131">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="154f8-132">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="154f8-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="154f8-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="154f8-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="154f8-134">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="154f8-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="154f8-135">Este exemplo mostra como usar o [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar a opção `max text repl size` como `-1`.</span><span class="sxs-lookup"><span data-stu-id="154f8-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max text repl size` option to `-1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;   
RECONFIGURE ;   
GO  
EXEC sp_configure 'max text repl size', -1 ;   
GO  
RECONFIGURE;   
GO  
  
```  
  
 <span data-ttu-id="154f8-136">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="154f8-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-text-repl-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="154f8-137">Acompanhamento: depois de configurar a opção max text repl size</span><span class="sxs-lookup"><span data-stu-id="154f8-137">Follow Up: After you configure the max text repl size option</span></span>  
 <span data-ttu-id="154f8-138">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="154f8-138">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154f8-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="154f8-139">See Also</span></span>  
 <span data-ttu-id="154f8-140">[Replicação do SQL Server](../../relational-databases/replication/sql-server-replication.md) </span><span class="sxs-lookup"><span data-stu-id="154f8-140">[SQL Server Replication](../../relational-databases/replication/sql-server-replication.md) </span></span>  
 <span data-ttu-id="154f8-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="154f8-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="154f8-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="154f8-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="154f8-143">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="154f8-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="154f8-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="154f8-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="154f8-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="154f8-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 <span data-ttu-id="154f8-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="154f8-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span></span>  
 [<span data-ttu-id="154f8-147">WRITETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="154f8-147">WRITETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/writetext-transact-sql)  
  
  
