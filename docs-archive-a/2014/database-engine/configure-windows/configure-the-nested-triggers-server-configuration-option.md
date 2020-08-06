---
title: Configurar a opção de configuração de servidor nested triggers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- nested triggers option
ms.assetid: 29d7372b-d406-4a5b-80c6-a2d231d25211
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b27e185b0833f2e51be16393ff4d59a81046970
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575348"
---
# <a name="configure-the-nested-triggers-server-configuration-option"></a><span data-ttu-id="1a98d-102">Configurar a opção de configuração de servidor nested triggers</span><span class="sxs-lookup"><span data-stu-id="1a98d-102">Configure the nested triggers Server Configuration Option</span></span>
  <span data-ttu-id="1a98d-103">Este tópico descreve como configurar a opção de configuração de servidor **nested triggers** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a98d-103">This topic describes how to configure the **nested triggers** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1a98d-104">A opção **nested triggers** controla se um gatilho AFTER pode ser colocado em cascata.</span><span class="sxs-lookup"><span data-stu-id="1a98d-104">The **nested triggers** option controls whether an AFTER trigger can cascade.</span></span> <span data-ttu-id="1a98d-105">Ou seja, executar uma ação que inicia outro gatilho que inicia outro gatilho e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="1a98d-105">That is, perform an action that initiates another trigger, which initiates another trigger, and so on.</span></span> <span data-ttu-id="1a98d-106">Quando **nested triggers** é definido como 0, os gatilhos AFTER não podem ser colocados em cascata.</span><span class="sxs-lookup"><span data-stu-id="1a98d-106">When **nested triggers** is set to 0, AFTER triggers cannot cascade.</span></span> <span data-ttu-id="1a98d-107">Quando **nested triggers** é definido como 1 (o padrão), os gatilhos AFTER podem ser colocados em cascata em até 32 níveis.</span><span class="sxs-lookup"><span data-stu-id="1a98d-107">When **nested triggers** is set to 1 (the default), AFTER triggers can cascade to as many as 32 levels.</span></span> <span data-ttu-id="1a98d-108">Gatilhos INSTEAD OF podem ser aninhados, independentemente da configuração dessa opção.</span><span class="sxs-lookup"><span data-stu-id="1a98d-108">INSTEAD OF triggers can be nested regardless of the setting of this option.</span></span>  
  
 <span data-ttu-id="1a98d-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="1a98d-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1a98d-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="1a98d-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1a98d-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="1a98d-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1a98d-112">**Para configurar a opção nested triggers usando:**</span><span class="sxs-lookup"><span data-stu-id="1a98d-112">**To configure the nested triggers option, using:**</span></span>  
  
     [<span data-ttu-id="1a98d-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a98d-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1a98d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a98d-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="1a98d-115">**Acompanhamento:**  [depois de configurar a opção nested triggers](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1a98d-115">**Follow Up:**  [After you configure the nested triggers option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1a98d-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1a98d-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1a98d-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="1a98d-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1a98d-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="1a98d-118">Permissions</span></span>  
 <span data-ttu-id="1a98d-119">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="1a98d-119">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="1a98d-120">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="1a98d-120">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="1a98d-121">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="1a98d-121">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a98d-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a98d-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="1a98d-123">Para configurar a opção nested triggers</span><span class="sxs-lookup"><span data-stu-id="1a98d-123">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="1a98d-124">No **Pesquisador de Objetos**, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1a98d-124">In **Object Explorer**, right-click a server, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1a98d-125">Na página **Avançado** , defina a opção **Permitir que Gatilhos Disparem Outros Gatilhos** como **Verdadeiro** (o padrão) ou **Falso**.</span><span class="sxs-lookup"><span data-stu-id="1a98d-125">On the **Advanced** page, set the **Allow Triggers to Fire Others** option to **True** (the default) or **False**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1a98d-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a98d-126">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="1a98d-127">Para configurar a opção nested triggers</span><span class="sxs-lookup"><span data-stu-id="1a98d-127">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="1a98d-128">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a98d-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1a98d-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1a98d-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1a98d-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1a98d-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1a98d-131">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `nested triggers` como `0`.</span><span class="sxs-lookup"><span data-stu-id="1a98d-131">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `nested triggers` option to `0`.</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'nested triggers', 0 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="1a98d-132">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1a98d-132">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-nested-triggers-option"></a><a name="FollowUp"></a> <span data-ttu-id="1a98d-133">Acompanhamento: depois de configurar a opção nested triggers</span><span class="sxs-lookup"><span data-stu-id="1a98d-133">Follow Up: After you configure the nested triggers option</span></span>  
 <span data-ttu-id="1a98d-134">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="1a98d-134">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a98d-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a98d-135">See Also</span></span>  
 <span data-ttu-id="1a98d-136">[Criar gatilhos aninhados](../../relational-databases/triggers/create-nested-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="1a98d-136">[Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md) </span></span>  
 <span data-ttu-id="1a98d-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a98d-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="1a98d-138">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1a98d-138">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="1a98d-139">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a98d-139">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
