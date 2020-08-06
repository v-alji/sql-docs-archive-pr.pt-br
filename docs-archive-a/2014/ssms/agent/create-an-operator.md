---
title: Criar um operador | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- jobs [SQL Server Agent], notification options
- operators (users) [Database Engine], creating with Management Studio
- SQL Server Agent jobs, notification options
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 1359d790-5905-4927-a208-e7155e7768a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfe07042f9a4b8ac595ada8b86e7bad131032700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680305"
---
# <a name="create-an-operator"></a><span data-ttu-id="4a881-102">Create an Operator</span><span class="sxs-lookup"><span data-stu-id="4a881-102">Create an Operator</span></span>
  <span data-ttu-id="4a881-103">Este tópico descreve como configurar um usuário para receber notificações sobre [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a881-103">This topic describes how to configure a user to receive notifications about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4a881-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4a881-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4a881-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4a881-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4a881-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4a881-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4a881-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="4a881-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4a881-108">**Para criar um operador usando:**</span><span class="sxs-lookup"><span data-stu-id="4a881-108">**To create an operator, using:**</span></span>  
  
     [<span data-ttu-id="4a881-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a881-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4a881-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a881-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4a881-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4a881-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4a881-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4a881-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4a881-113">As opções Pager e **net send** serão removidas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma versão futura do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a881-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4a881-114">Evite usar esses recursos em novo trabalho de desenvolvimento e planeje modificar os aplicativos que os usam atualmente.</span><span class="sxs-lookup"><span data-stu-id="4a881-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="4a881-115">Observe que o SQL Server Agent deve ser configurado para usar o Database Mail a fim de enviar notificações por pager ou email a operadores.</span><span class="sxs-lookup"><span data-stu-id="4a881-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="4a881-116">Para obter mais informações, consulte [Atribuir alertas a um operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4a881-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4a881-117">gerencia trabalhos de forma fácil e com representação gráfica. Além disso, ele é recomendado para criar e gerenciar a infraestrutura de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="4a881-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a881-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="4a881-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4a881-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="4a881-119">Permissions</span></span>  
 <span data-ttu-id="4a881-120">Somente membros da função de servidor fixa **sysadmin** podem criar operadores.</span><span class="sxs-lookup"><span data-stu-id="4a881-120">Only members of the **sysadmin** fixed server role can create operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a881-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a881-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="4a881-122">Para criar um operador</span><span class="sxs-lookup"><span data-stu-id="4a881-122">To create an operator</span></span>  
  
1.  <span data-ttu-id="4a881-123">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar o operador do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="4a881-123">In **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent operator.</span></span>  
  
2.  <span data-ttu-id="4a881-124">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="4a881-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4a881-125">Clique com o botão direito do mouse na pasta **Operadores** e selecione **Novo Operador**.</span><span class="sxs-lookup"><span data-stu-id="4a881-125">Right-click the **Operators** folder and select **New Operator**.</span></span>  
  
     <span data-ttu-id="4a881-126">As opções a seguir estão disponíveis na página **Geral** da caixa de diálogo **Novo Operador** :</span><span class="sxs-lookup"><span data-stu-id="4a881-126">The following options are available on the **General** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="4a881-127">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4a881-127">**Name**</span></span>  
     <span data-ttu-id="4a881-128">Altera o nome do operador.</span><span class="sxs-lookup"><span data-stu-id="4a881-128">Change the name of the operator.</span></span>  
  
     <span data-ttu-id="4a881-129">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="4a881-129">**Enabled**</span></span>  
     <span data-ttu-id="4a881-130">Habilita o operador.</span><span class="sxs-lookup"><span data-stu-id="4a881-130">Enable the operator.</span></span> <span data-ttu-id="4a881-131">Quando não estiver habilitado, nenhuma notificação será enviada ao operador.</span><span class="sxs-lookup"><span data-stu-id="4a881-131">When not enabled, no notifications are sent to the operator.</span></span>  
  
     <span data-ttu-id="4a881-132">**Nome de email**</span><span class="sxs-lookup"><span data-stu-id="4a881-132">**E-mail name**</span></span>  
     <span data-ttu-id="4a881-133">Especifica o endereço de email do operador.</span><span class="sxs-lookup"><span data-stu-id="4a881-133">Specifies the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="4a881-134">**Endereço de net send**</span><span class="sxs-lookup"><span data-stu-id="4a881-134">**Net send address**</span></span>  
     <span data-ttu-id="4a881-135">Especifique o endereço a ser usado para **net send**.</span><span class="sxs-lookup"><span data-stu-id="4a881-135">Specify the address to use for **net send**.</span></span>  
  
     <span data-ttu-id="4a881-136">**Nome de e-mail de pager**</span><span class="sxs-lookup"><span data-stu-id="4a881-136">**Pager e-mail name**</span></span>  
     <span data-ttu-id="4a881-137">Especifica o endereço de email a ser usado para o pager do operador.</span><span class="sxs-lookup"><span data-stu-id="4a881-137">Specifies the e-mail address to use for the operator's pager.</span></span>  
  
     <span data-ttu-id="4a881-138">**Agenda em serviço do pager**</span><span class="sxs-lookup"><span data-stu-id="4a881-138">**Pager on duty schedule**</span></span>  
     <span data-ttu-id="4a881-139">Marca as horas em que o pager está ativo.</span><span class="sxs-lookup"><span data-stu-id="4a881-139">Sets the times at which the pager is active.</span></span>  
  
     <span data-ttu-id="4a881-140">**Segunda-feira - Domingo**</span><span class="sxs-lookup"><span data-stu-id="4a881-140">**Monday - Sunday**</span></span>  
     <span data-ttu-id="4a881-141">Selecione os dias em que o pager está ativo.</span><span class="sxs-lookup"><span data-stu-id="4a881-141">Select the days that the pager is active.</span></span>  
  
     <span data-ttu-id="4a881-142">**Início do dia útil**</span><span class="sxs-lookup"><span data-stu-id="4a881-142">**Workday begin**</span></span>  
     <span data-ttu-id="4a881-143">Selecione a hora do dia depois da qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent envia mensagens ao pager.</span><span class="sxs-lookup"><span data-stu-id="4a881-143">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sends messages to the pager.</span></span>  
  
     <span data-ttu-id="4a881-144">**Término do dia útil**</span><span class="sxs-lookup"><span data-stu-id="4a881-144">**Workday end**</span></span>  
     <span data-ttu-id="4a881-145">Selecione a hora do dia depois da qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para de enviar mensagens ao pager.</span><span class="sxs-lookup"><span data-stu-id="4a881-145">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer sends messages to the pager.</span></span>  
  
     <span data-ttu-id="4a881-146">As opções a seguir estão disponíveis na página **Notificações** da caixa de diálogo **Novo Operador** :</span><span class="sxs-lookup"><span data-stu-id="4a881-146">The following options are available on the **Notifications** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="4a881-147">**Alertas**</span><span class="sxs-lookup"><span data-stu-id="4a881-147">**Alerts**</span></span>  
     <span data-ttu-id="4a881-148">Exiba os alertas na instância.</span><span class="sxs-lookup"><span data-stu-id="4a881-148">View the alerts in the instance.</span></span>  
  
     <span data-ttu-id="4a881-149">**Trabalhos**</span><span class="sxs-lookup"><span data-stu-id="4a881-149">**Jobs**</span></span>  
     <span data-ttu-id="4a881-150">Exiba os trabalhos na instância.</span><span class="sxs-lookup"><span data-stu-id="4a881-150">View the jobs in the instance.</span></span>  
  
     <span data-ttu-id="4a881-151">**Lista de alertas**</span><span class="sxs-lookup"><span data-stu-id="4a881-151">**Alert list**</span></span>  
     <span data-ttu-id="4a881-152">Lista os alertas na instância.</span><span class="sxs-lookup"><span data-stu-id="4a881-152">Lists the alerts in the instance.</span></span>  
  
     <span data-ttu-id="4a881-153">**Lista de trabalhos**</span><span class="sxs-lookup"><span data-stu-id="4a881-153">**Job list**</span></span>  
     <span data-ttu-id="4a881-154">Lista os trabalhos na instância.</span><span class="sxs-lookup"><span data-stu-id="4a881-154">Lists the jobs in the instance.</span></span>  
  
     <span data-ttu-id="4a881-155">**Mensagens**</span><span class="sxs-lookup"><span data-stu-id="4a881-155">**E-mail**</span></span>  
     <span data-ttu-id="4a881-156">Notifique este operador por email.</span><span class="sxs-lookup"><span data-stu-id="4a881-156">Notify this operator using e-mail.</span></span>  
  
     <span data-ttu-id="4a881-157">**Pager**</span><span class="sxs-lookup"><span data-stu-id="4a881-157">**Pager**</span></span>  
     <span data-ttu-id="4a881-158">Notifique este operador enviando e-mail ao endereço de pager.</span><span class="sxs-lookup"><span data-stu-id="4a881-158">Notify this operator by sending e-mail to the pager address.</span></span>  
  
     <span data-ttu-id="4a881-159">**Net send**</span><span class="sxs-lookup"><span data-stu-id="4a881-159">**Net send**</span></span>  
     <span data-ttu-id="4a881-160">Notifique este operador pelo **net send**.</span><span class="sxs-lookup"><span data-stu-id="4a881-160">Notify this operator using **net send**.</span></span>  
  
4.  <span data-ttu-id="4a881-161">Quando terminar de criar o novo operador, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a881-161">When finished creating the new operator, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a881-162">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a881-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="4a881-163">Para criar um operador</span><span class="sxs-lookup"><span data-stu-id="4a881-163">To create an operator</span></span>  
  
1.  <span data-ttu-id="4a881-164">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a881-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4a881-165">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4a881-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4a881-166">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4a881-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- sets up the operator information for user 'danwi.' The operator is enabled.   
    -- SQL Server Agent sends notifications by pager from Monday through Friday from 8 A.M. to 5 P.M.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_operator  
        @name = N'Dan Wilson',  
        @enabled = 1,  
        @email_address = N'danwi',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 62 ;  
    GO  
    ```  
  
 <span data-ttu-id="4a881-167">Para obter mais informações, consulte [sp_add_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4a881-167">For more information, see [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span></span>  
  
  
