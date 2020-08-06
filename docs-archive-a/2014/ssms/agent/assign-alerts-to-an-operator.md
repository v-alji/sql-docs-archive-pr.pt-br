---
title: Atribuir alertas a um operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- assigning alerts to operator
- SQL Server Agent, alerts
- alerts [SQL Server], assigning to operator
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: aa818155-6fa2-4565-a09f-5c7e31c89754
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cc238b952c03595035856f377b6fdbb9eaf5e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573373"
---
# <a name="assign-alerts-to-an-operator"></a><span data-ttu-id="9497a-102">Assign Alerts to an Operator</span><span class="sxs-lookup"><span data-stu-id="9497a-102">Assign Alerts to an Operator</span></span>
  <span data-ttu-id="9497a-103">Este tópico descreve como atribuir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas de agente aos operadores para que eles possam receber notificações sobre trabalhos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9497a-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts to operators so they can receive notifications about jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9497a-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="9497a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9497a-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="9497a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9497a-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9497a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9497a-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="9497a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9497a-108">**Para atribuir alertas a um operador, usando:**</span><span class="sxs-lookup"><span data-stu-id="9497a-108">**To assign alerts to an operator, using:**</span></span>  
  
     [<span data-ttu-id="9497a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9497a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9497a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9497a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9497a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9497a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9497a-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9497a-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="9497a-113">fornece um modo fácil e gráfico para gerenciar o sistema de alertas inteiro.</span><span class="sxs-lookup"><span data-stu-id="9497a-113">provides an easy, graphical way to manage the entire alerting system.</span></span> <span data-ttu-id="9497a-114">Usar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] é o modo recomendado de configuração de sua infraestrutura de alerta.</span><span class="sxs-lookup"><span data-stu-id="9497a-114">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is the recommended way to configure your alert infrastructure.</span></span>  
  
-   <span data-ttu-id="9497a-115">Para enviar uma notificação em resposta a um alerta, primeiro você deve configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para enviar email.</span><span class="sxs-lookup"><span data-stu-id="9497a-115">To send a notification in response to an alert, you must first configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send mail.</span></span> <span data-ttu-id="9497a-116">Para obter mais informações, consulte [Configurar o SQL Server Agent Mail para usar o Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="9497a-116">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
-   <span data-ttu-id="9497a-117">Se ocorrer uma falha ao enviar uma mensagem de email ou uma notificação de pager, a falha será relatada no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="9497a-117">If a failure occurs when sending an e-mail message or pager notification, the failure is reported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service error log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9497a-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="9497a-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9497a-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="9497a-119">Permissions</span></span>  
 <span data-ttu-id="9497a-120">Somente membros da função de servidor fixa **sysadmin** podem atribuir alertas a operadores.</span><span class="sxs-lookup"><span data-stu-id="9497a-120">Only members of the **sysadmin** fixed server role can assign alerts to operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9497a-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9497a-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="9497a-122">Para atribuir alertas a um operador</span><span class="sxs-lookup"><span data-stu-id="9497a-122">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="9497a-123">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o operador ao qual você deseja atribuir um alerta.</span><span class="sxs-lookup"><span data-stu-id="9497a-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator to which you want to assign an alert.</span></span>  
  
2.  <span data-ttu-id="9497a-124">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="9497a-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="9497a-125">Clique no sinal de adição para expandir a pasta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="9497a-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="9497a-126">Clique com o botão direito do mouse no operador ao qual você deseja atribuir um alerta e selecione **Propriedades**e a página **Notificações** .</span><span class="sxs-lookup"><span data-stu-id="9497a-126">Right-click the operator to which you want to assign an alert and select **Properties**, and select the **Notifications** page.</span></span>  
  
5.  <span data-ttu-id="9497a-127">Na caixa de diálogo**Propriedades** do _Operator_name_, em **selecionar uma página**, selecione **notificações**.</span><span class="sxs-lookup"><span data-stu-id="9497a-127">In the _operator_name_**Properties** dialog box, under **Select a page**, select **Notifications**.</span></span>  
  
6.  <span data-ttu-id="9497a-128">Em **Exibir notificações enviadas a esse usuário por**, selecione **Alertas** , para visualizar uma lista dos alertas enviados ao operador, ou **Trabalhos** , para visualizar uma lista dos trabalhos que enviam notificações ao operador.</span><span class="sxs-lookup"><span data-stu-id="9497a-128">Under **View notifications sent to this user by**, select **Alerts** to view a list of alerts sent to this operator or select **Jobs** to view a list of jobs that send notifications to this operator.</span></span> <span data-ttu-id="9497a-129">Marque uma ou mais das seguintes caixas de seleção para definir o método de cada notificação, conforme a necessidade: **Email**, **Pager**ou **Net send**.</span><span class="sxs-lookup"><span data-stu-id="9497a-129">Select one or more of the following checkboxes to define the notification method for each notification as necessary: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="9497a-130">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9497a-130">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9497a-131">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9497a-131">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="9497a-132">Para atribuir alertas a um operador</span><span class="sxs-lookup"><span data-stu-id="9497a-132">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="9497a-133">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9497a-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9497a-134">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="9497a-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9497a-135">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9497a-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for the specified alert (Test Alert)  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="9497a-136">Para obter mais informações, consulte [sp_add_notification &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9497a-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
