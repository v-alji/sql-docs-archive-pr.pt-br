---
title: Configurar a opção de configuração de servidor priority boost | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- priority boost option
ms.assetid: 765f1e83-dd52-44fb-b0c8-1078f213607b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f42d7d2022e07dcac3039557295dc70e4500583d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572175"
---
# <a name="configure-the-priority-boost-server-configuration-option"></a><span data-ttu-id="29c95-102">Configurar a opção de configuração de servidor de aumento de prioridade</span><span class="sxs-lookup"><span data-stu-id="29c95-102">Configure the priority boost Server Configuration Option</span></span>
  <span data-ttu-id="29c95-103">Este tópico descreve como configurar a opção de configuração **aumento de prioridade** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29c95-103">This topic describes how to configure the **priority boost** configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="29c95-104">Use a opção **aumento de prioridade** para especificar se o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser executado em uma prioridade mais alta de agendamento do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 ou Windows 2008 R2 do que outros processos no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="29c95-104">Use the **priority boost** option to specify whether [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 or Windows 2008 R2 scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="29c95-105">Se você definir essa opção como 1, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executará em uma base de prioridade de 13 no agendador do Windows 2008 ou do Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="29c95-105">If you set this option to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs at a priority base of 13 in the Windows 2008 or Windows Server 2008 R2 scheduler.</span></span> <span data-ttu-id="29c95-106">O padrão é 0, que é uma base de prioridade de 7.</span><span class="sxs-lookup"><span data-stu-id="29c95-106">The default is 0, which is a priority base of 7.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="29c95-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="29c95-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="29c95-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="29c95-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="29c95-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="29c95-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="29c95-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="29c95-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="29c95-111">**Para configurar a opção de aumento de prioridade usando:**</span><span class="sxs-lookup"><span data-stu-id="29c95-111">**To configure the priority boost option, using:**</span></span>  
  
     [<span data-ttu-id="29c95-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29c95-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="29c95-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29c95-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="29c95-114">**Acompanhamento:**  [depois de configurar a opção priority boost](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="29c95-114">**Follow Up:**  [After you configure the priority boost option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29c95-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="29c95-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="29c95-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="29c95-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="29c95-117">Aumentar demais a prioridade pode esgotar os recursos das funções essenciais do sistema operacional e de rede, o que resulta em problemas para desligar o SQL Server ou usar outras tarefas do sistema operacional no servidor.</span><span class="sxs-lookup"><span data-stu-id="29c95-117">Raising the priority too high may drain resources from essential operating system and network functions, resulting in problems shutting down SQL Server or using other operating system tasks on the server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29c95-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="29c95-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="29c95-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="29c95-119">Permissions</span></span>  
 <span data-ttu-id="29c95-120">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="29c95-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="29c95-121">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="29c95-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="29c95-122">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="29c95-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="29c95-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29c95-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="29c95-124">Para configurar a opção de aumento de prioridade</span><span class="sxs-lookup"><span data-stu-id="29c95-124">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="29c95-125">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="29c95-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="29c95-126">Clique no nó **Processadores** .</span><span class="sxs-lookup"><span data-stu-id="29c95-126">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="29c95-127">Em **Threads**, marque a caixa de seleção **Aumentar a prioridade do SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="29c95-127">Under **Threads**, select the **Boost SQL Server priority** check box.</span></span>  
  
4.  <span data-ttu-id="29c95-128">Interrompa e reinicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29c95-128">Stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="29c95-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="29c95-129">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="29c95-130">Para configurar a opção de aumento de prioridade</span><span class="sxs-lookup"><span data-stu-id="29c95-130">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="29c95-131">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29c95-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="29c95-132">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="29c95-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="29c95-133">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="29c95-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="29c95-134">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `priority boost` como `1`.</span><span class="sxs-lookup"><span data-stu-id="29c95-134">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `priority boost` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'priority boost', 1 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="29c95-135">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="29c95-135">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-priority-boost-option"></a><a name="FollowUp"></a> <span data-ttu-id="29c95-136">Acompanhamento: depois de configurar a opção priority boost</span><span class="sxs-lookup"><span data-stu-id="29c95-136">Follow Up: After you configure the priority boost option</span></span>  
 <span data-ttu-id="29c95-137">O servidor deve ser reiniciado para que a configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="29c95-137">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c95-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29c95-138">See Also</span></span>  
 <span data-ttu-id="29c95-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="29c95-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="29c95-140">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29c95-140">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="29c95-141">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29c95-141">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
