---
title: Configurar a opção de configuração de servidor remote proc trans | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote proc trans option
- distributed transactions [SQL Server], enforcing
ms.assetid: cfbc6158-ab96-44b4-87eb-ea278c1b0c6b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54fcaafa51eef33acb1ae8d1e2f36022840b76a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572172"
---
# <a name="configure-the-remote-proc-trans-server-configuration-option"></a><span data-ttu-id="4dbfd-102">Configurar a opção remote proc trans de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="4dbfd-102">Configure the remote proc trans Server Configuration Option</span></span>
  <span data-ttu-id="4dbfd-103">Este tópico descreve como configurar a opção de configuração de servidor **remote proc trans** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dbfd-103">This topic describes how to configure the **remote proc trans** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4dbfd-104">A opção **remote proc trans** ajuda a proteger as ações de um procedimento servidor-para-servidor por meio de uma transação MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="4dbfd-104">The **remote proc trans** option helps protect the actions of a server-to-server procedure through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) transaction.</span></span>  
  
 <span data-ttu-id="4dbfd-105">Defina o valor de **remote proc trans** como 1 para fornecer uma transação distribuída coordenada pelo MS DTC que protege as propriedades ACID (atômica, consistente, isolada e durável) das transações.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-105">Set the value of **remote proc trans** to 1 to provide an MS DTC-coordinated distributed transaction that protects the ACID (atomic, consistent, isolated, and durable) properties of transactions.</span></span> <span data-ttu-id="4dbfd-106">As sessões iniciadas após a definição dessa opção como 1 herdam os parâmetros de configuração como padrão.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-106">Sessions begun after setting this option to 1 inherit the configuration setting as their default.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 <span data-ttu-id="4dbfd-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4dbfd-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4dbfd-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4dbfd-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4dbfd-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4dbfd-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="4dbfd-110">Recomendações</span><span class="sxs-lookup"><span data-stu-id="4dbfd-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4dbfd-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="4dbfd-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4dbfd-112">**Para configurar a opção remote proc trans, usando:**</span><span class="sxs-lookup"><span data-stu-id="4dbfd-112">**To configure the remote proc trans option, using:**</span></span>  
  
     [<span data-ttu-id="4dbfd-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4dbfd-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4dbfd-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4dbfd-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4dbfd-115">**Acompanhamento:**  [depois de configurar a opção remote proc trans](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4dbfd-115">**Follow Up:**  [After you configure the remote proc trans option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4dbfd-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4dbfd-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4dbfd-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4dbfd-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="4dbfd-118">Devem ser permitidas conexões de servidor remoto antes que este valor possa ser definido.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-118">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4dbfd-119">Recomendações</span><span class="sxs-lookup"><span data-stu-id="4dbfd-119">Recommendations</span></span>  
  
-   <span data-ttu-id="4dbfd-120">Essa opção é fornecida para compatibilidade com versões anteriores do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em aplicativos que usam procedimentos armazenados remotos.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-120">This option is provided for compatibility with earlier versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for applications that use remote stored procedures.</span></span> <span data-ttu-id="4dbfd-121">Em vez de emitir chamadas a procedimentos armazenados remotos, use consultas distribuídas que fazem referência a servidores vinculados, definidos com [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4dbfd-121">Instead of issuing remote stored procedure calls, use distributed queries that reference linked servers, which are defined by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4dbfd-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="4dbfd-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4dbfd-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="4dbfd-123">Permissions</span></span>  
 <span data-ttu-id="4dbfd-124">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="4dbfd-125">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="4dbfd-126">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="4dbfd-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4dbfd-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4dbfd-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="4dbfd-128">Para configurar a opção remote proc trans</span><span class="sxs-lookup"><span data-stu-id="4dbfd-128">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="4dbfd-129">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4dbfd-130">Clique no nó **Conexões** .</span><span class="sxs-lookup"><span data-stu-id="4dbfd-130">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="4dbfd-131">Em **Conexões de servidor remoto**, marque a caixa de seleção **Requer transações distribuídas para servidor para comunicação de servidor** .</span><span class="sxs-lookup"><span data-stu-id="4dbfd-131">Under **Remote server connections**, select the **Require Distributed Transactions for server to server communication** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4dbfd-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4dbfd-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="4dbfd-133">Para configurar a opção remote proc trans</span><span class="sxs-lookup"><span data-stu-id="4dbfd-133">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="4dbfd-134">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dbfd-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4dbfd-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4dbfd-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4dbfd-137">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `remote proc trans` como `1`.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote proc trans` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote proc trans', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="4dbfd-138">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dbfd-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-proc-trans-option"></a><a name="FollowUp"></a> <span data-ttu-id="4dbfd-139">Acompanhamento: depois de configurar a opção remote proc trans</span><span class="sxs-lookup"><span data-stu-id="4dbfd-139">Follow Up: After you configure the remote proc trans option</span></span>  
 <span data-ttu-id="4dbfd-140">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="4dbfd-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dbfd-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4dbfd-141">See Also</span></span>  
 <span data-ttu-id="4dbfd-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dbfd-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="4dbfd-143">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dbfd-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="4dbfd-144">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4dbfd-144">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
