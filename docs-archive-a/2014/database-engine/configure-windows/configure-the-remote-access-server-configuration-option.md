---
title: Configurar a opção de configuração de servidor remote access | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], stored procedure execution
ms.assetid: f5de748d-1c55-4714-9661-38fe62e5095f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eef18ec48ede59544b13545e49dc105909cfac16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570237"
---
# <a name="configure-the-remote-access-server-configuration-option"></a><span data-ttu-id="d0fcc-102">Configurar a opção remote access de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="d0fcc-102">Configure the remote access Server Configuration Option</span></span>
  <span data-ttu-id="d0fcc-103">Este tópico descreve como configurar a opção de configuração de servidor **remote access** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0fcc-103">This topic describes how to configure the **remote access** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d0fcc-104">A opção **remote access** controla a execução de procedimentos armazenados de servidores locais ou remotos nos quais instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estão sendo executadas.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-104">The **remote access** option controls the execution of stored procedures from local or remote servers on which instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are running.</span></span> <span data-ttu-id="d0fcc-105">O valor padrão dessa opção é 1.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-105">This default value for this option is 1.</span></span> <span data-ttu-id="d0fcc-106">Isso concede permissão para executar procedimentos armazenados locais de servidores remotos ou procedimentos armazenados remotos do servidor local.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-106">This grants permission to run local stored procedures from remote servers or remote stored procedures from the local server.</span></span> <span data-ttu-id="d0fcc-107">Para evitar que procedimentos armazenados locais sejam executados a partir de um servidor remoto ou que procedimentos armazenados remotos sejam executados no servidor local, defina a opção como 0.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-107">To prevent local stored procedures from being run from a remote server or remote stored procedures from being run on the local server, set the option to 0.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="d0fcc-108">Em vez disso, use [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d0fcc-108">Use [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="d0fcc-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="d0fcc-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d0fcc-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="d0fcc-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d0fcc-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="d0fcc-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d0fcc-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="d0fcc-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d0fcc-113">**Para configurar a opção remote access, usando:**</span><span class="sxs-lookup"><span data-stu-id="d0fcc-113">**To configure the remote access option, using:**</span></span>  
  
     [<span data-ttu-id="d0fcc-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0fcc-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d0fcc-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0fcc-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d0fcc-116">**Acompanhamento:**  [depois de configurar a opção remote access](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d0fcc-116">**Follow Up:**  [After you configure the remote access option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0fcc-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d0fcc-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d0fcc-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="d0fcc-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d0fcc-119">A opção **remote access** se aplica apenas aos servidores que são adicionados usando [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)e está incluída para ter compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-119">The **remote access** option only applies to servers that are added by using [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), and is included for backward compatibility.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d0fcc-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="d0fcc-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d0fcc-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="d0fcc-121">Permissions</span></span>  
 <span data-ttu-id="d0fcc-122">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="d0fcc-123">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="d0fcc-124">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="d0fcc-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d0fcc-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0fcc-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="d0fcc-126">Para configurar a opção remote access</span><span class="sxs-lookup"><span data-stu-id="d0fcc-126">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="d0fcc-127">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d0fcc-128">Clique no nó **Conexões** .</span><span class="sxs-lookup"><span data-stu-id="d0fcc-128">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="d0fcc-129">Em **Conexões do servidor remoto**, marque ou desmarque a caixa de seleção **Permitir conexões remotas com este servidor** .</span><span class="sxs-lookup"><span data-stu-id="d0fcc-129">Under **Remote server connections**, select or clear the **Allow remote connections to this server** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d0fcc-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d0fcc-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="d0fcc-131">Para configurar a opção remote access</span><span class="sxs-lookup"><span data-stu-id="d0fcc-131">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="d0fcc-132">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0fcc-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d0fcc-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d0fcc-134">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d0fcc-135">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `remote access` como `0`.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote access` option to `0`.</span></span>  
  
```sql  
EXEC sp_configure 'remote access', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="d0fcc-136">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d0fcc-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-access-option"></a><a name="FollowUp"></a> <span data-ttu-id="d0fcc-137">Acompanhamento: depois de configurar a opção remote access</span><span class="sxs-lookup"><span data-stu-id="d0fcc-137">Follow Up: After you configure the remote access option</span></span>  
 <span data-ttu-id="d0fcc-138">Essa configuração não entrará em vigor até que você reinicie o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d0fcc-138">This setting does not take effect until you restart SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fcc-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0fcc-139">See Also</span></span>  
 <span data-ttu-id="d0fcc-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d0fcc-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="d0fcc-141">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d0fcc-141">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="d0fcc-142">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d0fcc-142">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
