---
title: Configurar a opção de configuração de servidor remote query timeout | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- time limit for remote queries [SQL Server]
- remote query timeout option
ms.assetid: 888c8448-933b-41e3-8aa1-c206bc0cdb78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 74f82d621d7f0375a6a3ca604abba00f83fc6024
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684897"
---
# <a name="configure-the-remote-query-timeout-server-configuration-option"></a><span data-ttu-id="66d59-102">Configurar a opção de configuração de servidor remote query timeout</span><span class="sxs-lookup"><span data-stu-id="66d59-102">Configure the remote query timeout Server Configuration Option</span></span>
  <span data-ttu-id="66d59-103">Este tópico descreve como configurar a opção de configuração de servidor **remote query timeout** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66d59-103">This topic describes how to configure the **remote query timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="66d59-104">A opção **remote query timeout** especifica quanto tempo, em segundos, uma operação remota pode levar antes de o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exceder o tempo limite. O valor padrão para essa opção é 600, o que permite uma espera de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="66d59-104">The **remote query timeout** option specifies how long, in seconds, a remote operation can take before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] times out. The default value for this option is 600, which allows a 10-minute wait.</span></span> <span data-ttu-id="66d59-105">Esse valor é aplicado a uma conexão de saída iniciada pelo [!INCLUDE[ssDE](../../includes/ssde-md.md)] como uma consulta remota.</span><span class="sxs-lookup"><span data-stu-id="66d59-105">This value applies to an outgoing connection initiated by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] as a remote query.</span></span> <span data-ttu-id="66d59-106">Esse valor não tem nenhum efeito em consultas recebidas pelo [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66d59-106">This value has no effect on queries received by the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="66d59-107">Para desabilitar o tempo limite, defina o valor como 0.</span><span class="sxs-lookup"><span data-stu-id="66d59-107">To disable the time-out, set the value to 0.</span></span> <span data-ttu-id="66d59-108">Uma consulta aguardará até ser concluída.</span><span class="sxs-lookup"><span data-stu-id="66d59-108">A query will wait until it completes.</span></span>  
  
 <span data-ttu-id="66d59-109">Para consultas heterogêneas, **remote query timeout** especifica o número de segundos (inicializado no objeto de comando usando a propriedade de conjunto de linhas DBPROP_COMMANDTIMEOUT) que um provedor remoto deve esperar para os conjuntos de resultados antes de a consulta exceder o tempo limite. Esse valor é usado também para definir o DBPROP_GENERALTIMEOUT se o provedor remoto oferecer suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="66d59-109">For heterogeneous queries, **remote query timeout** specifies the number of seconds (initialized in the command object using the DBPROP_COMMANDTIMEOUT rowset property) that a remote provider should wait for result sets before the query times out. This value is also used to set DBPROP_GENERALTIMEOUT if supported by the remote provider.</span></span> <span data-ttu-id="66d59-110">Isso fará com que qualquer outra operação exceda o tempo limite depois do número especificado de segundos.</span><span class="sxs-lookup"><span data-stu-id="66d59-110">This will cause any other operations to time out after the specified number of seconds.</span></span>  
  
 <span data-ttu-id="66d59-111">Para procedimentos armazenados remotos, **remote query timeout** especifica o número de segundos que devem decorrer depois de enviar uma instrução remota `EXEC` antes de o procedimento armazenado remoto exceder o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="66d59-111">For remote stored procedures, **remote query timeout** specifies the number of seconds that must elapse after sending a remote `EXEC` statement before the remote stored procedure times out.</span></span>  
  
 <span data-ttu-id="66d59-112">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="66d59-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="66d59-113">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="66d59-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="66d59-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="66d59-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="66d59-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="66d59-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="66d59-116">**Para configurar a opção remote query timeout usando:**</span><span class="sxs-lookup"><span data-stu-id="66d59-116">**To configure the remote query timeout option, using:**</span></span>  
  
     [<span data-ttu-id="66d59-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66d59-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="66d59-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66d59-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="66d59-119">**Acompanhamento:**  [depois de configurar a opção remote query timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="66d59-119">**Follow Up:**  [After you configure the remote query timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="66d59-120">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="66d59-120">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="66d59-121">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="66d59-121">Prerequisites</span></span>  
  
-   <span data-ttu-id="66d59-122">Devem ser permitidas conexões de servidor remoto antes que este valor possa ser definido.</span><span class="sxs-lookup"><span data-stu-id="66d59-122">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="66d59-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="66d59-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="66d59-124">Permissões</span><span class="sxs-lookup"><span data-stu-id="66d59-124">Permissions</span></span>  
 <span data-ttu-id="66d59-125">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="66d59-125">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="66d59-126">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="66d59-126">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="66d59-127">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="66d59-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="66d59-128">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66d59-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="66d59-129">Para configurar a opção remote query timeout</span><span class="sxs-lookup"><span data-stu-id="66d59-129">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="66d59-130">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="66d59-130">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="66d59-131">Clique no nó **Conexões** .</span><span class="sxs-lookup"><span data-stu-id="66d59-131">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="66d59-132">Em **Conexões do servidor remoto**, na caixa **Tempo limite de consulta remota** , digite ou selecione um valor de 0 a 2.147.483.647 para definir o número máximo de segundos que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve aguardar antes de o tempo limite ser excedido.</span><span class="sxs-lookup"><span data-stu-id="66d59-132">Under **Remote server connections**, in the **Remote query timeout** box, type or select a value from 0 through 2,147,483,647 to set the maximum number seconds for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to wait before timing out.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="66d59-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66d59-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="66d59-134">Para configurar a opção remote query timeout</span><span class="sxs-lookup"><span data-stu-id="66d59-134">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="66d59-135">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66d59-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="66d59-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="66d59-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="66d59-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="66d59-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="66d59-138">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `remote query timeout` como `0` para desabilitar o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="66d59-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote query timeout` option to `0` to disable the time-out.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote query timeout', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="66d59-139">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66d59-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-query-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="66d59-140">Acompanhamento: depois de configurar a opção remote query timeout</span><span class="sxs-lookup"><span data-stu-id="66d59-140">Follow Up: After you configure the remote query timeout option</span></span>  
 <span data-ttu-id="66d59-141">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="66d59-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d59-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66d59-142">See Also</span></span>  
 <span data-ttu-id="66d59-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="66d59-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="66d59-144">[Propriedades e comportamentos do conjunto de linhas](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="66d59-144">[Rowset Properties and Behaviors](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 <span data-ttu-id="66d59-145">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66d59-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="66d59-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="66d59-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
