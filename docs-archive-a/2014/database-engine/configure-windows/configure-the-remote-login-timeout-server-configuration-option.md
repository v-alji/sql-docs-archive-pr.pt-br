---
title: Configurar a opção de configuração de servidor remote login timeout | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote login timeout option
ms.assetid: 077adebe-0e3f-42a5-a75e-5e6d04847e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58b3405f9b0e51bd43edcaa31e84c8ebbcc48547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570234"
---
# <a name="configure-the-remote-login-timeout-server-configuration-option"></a><span data-ttu-id="d03c9-102">Configurar a opção de configuração de servidor remote login timeout</span><span class="sxs-lookup"><span data-stu-id="d03c9-102">Configure the remote login timeout Server Configuration Option</span></span>
  <span data-ttu-id="d03c9-103">Este tópico descreve como configurar a opção de configuração de servidor **remote login timeout** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d03c9-103">This topic describes how to configure the **remote login timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d03c9-104">A opção **remote login timeout** especifica quantos segundos será necessário esperar antes de retornar de uma tentativa malsucedida para fazer logon em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="d03c9-104">The **remote login timeout** option specifies the number of seconds to wait before returning from a failed attempt to log in to a remote server.</span></span> <span data-ttu-id="d03c9-105">Por exemplo, se você está tentando fazer logon em um servidor remoto e esse servidor está inoperante, o **remote login timeout** ajuda a assegurar que não seja necessário aguardar indefinidamente antes do computador cessar as tentativas de fazer logon.</span><span class="sxs-lookup"><span data-stu-id="d03c9-105">For example, if you are trying to log in to a remote server and that server is down, **remote login timeout** helps make sure that you do not have to wait indefinitely before your computer stops trying to log in.</span></span> <span data-ttu-id="d03c9-106">O valor padrão desta opção é 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="d03c9-106">The default value for this option is 10 seconds.</span></span> <span data-ttu-id="d03c9-107">Um valor 0 permite uma espera infinita.</span><span class="sxs-lookup"><span data-stu-id="d03c9-107">A value of 0 allows for an infinite wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d03c9-108">O valor padrão desta opção é 20 segundos no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d03c9-108">The default value for this option is 20 seconds in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="d03c9-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="d03c9-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d03c9-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="d03c9-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d03c9-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="d03c9-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d03c9-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="d03c9-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d03c9-113">**Para configurar a opção remote login timeout usando:**</span><span class="sxs-lookup"><span data-stu-id="d03c9-113">**To configure the remote login timeout option, using:**</span></span>  
  
     [<span data-ttu-id="d03c9-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d03c9-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d03c9-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d03c9-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d03c9-116">**Acompanhamento:**  [depois de configurar a opção remote login timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d03c9-116">**Follow Up:**  [After you configure the remote login timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d03c9-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d03c9-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d03c9-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="d03c9-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d03c9-119">A opção **remote login timeout** afeta conexões com provedores OLE DB feitas para consultas heterogêneas.</span><span class="sxs-lookup"><span data-stu-id="d03c9-119">The **remote login timeout** option affects connections to OLE DB providers made for heterogeneous queries.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d03c9-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="d03c9-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d03c9-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="d03c9-121">Permissions</span></span>  
 <span data-ttu-id="d03c9-122">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="d03c9-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="d03c9-123">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="d03c9-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="d03c9-124">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="d03c9-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d03c9-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d03c9-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="d03c9-126">Para configurar a opção remote login timeout</span><span class="sxs-lookup"><span data-stu-id="d03c9-126">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="d03c9-127">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d03c9-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d03c9-128">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="d03c9-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="d03c9-129">Em **Rede**, selecione um valor para a caixa **Tempo Limite de Logon Remoto** .</span><span class="sxs-lookup"><span data-stu-id="d03c9-129">Under **Network**, select a value for the **Remote Login Timeout** box.</span></span>  
  
     <span data-ttu-id="d03c9-130">Use a opção **remote login timeout** para especificar quantos segundos esperar antes de retornar de uma tentativa malsucedida de fazer o logon remoto.</span><span class="sxs-lookup"><span data-stu-id="d03c9-130">Use the **remote login timeout** option to specify the number of seconds to wait before returning from a failed remote login attempt.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d03c9-131">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d03c9-131">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="d03c9-132">Para configurar a opção remote login timeout</span><span class="sxs-lookup"><span data-stu-id="d03c9-132">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="d03c9-133">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d03c9-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d03c9-134">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d03c9-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d03c9-135">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d03c9-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d03c9-136">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `remote login timeout` como `35` segundos.</span><span class="sxs-lookup"><span data-stu-id="d03c9-136">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote login timeout` option to `35` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote login timeout', 35 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="d03c9-137">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d03c9-137">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-login-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="d03c9-138">Acompanhamento: depois de configurar a opção remote login timeout</span><span class="sxs-lookup"><span data-stu-id="d03c9-138">Follow Up: After you configure the remote login timeout option</span></span>  
 <span data-ttu-id="d03c9-139">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="d03c9-139">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d03c9-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d03c9-140">See Also</span></span>  
 <span data-ttu-id="d03c9-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d03c9-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="d03c9-142">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d03c9-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="d03c9-143">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d03c9-143">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
