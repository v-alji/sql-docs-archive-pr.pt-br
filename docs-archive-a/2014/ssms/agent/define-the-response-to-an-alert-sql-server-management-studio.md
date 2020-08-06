---
title: Definir a resposta a um alerta (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], responding to
- responding to alerts
ms.assetid: c86ca6eb-c59f-46e9-bc32-d474e7c3b170
author: stevestein
ms.author: sstein
ms.openlocfilehash: c14e5adf43602b57697483b9ce4c2cdf20ff8e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680292"
---
# <a name="define-the-response-to-an-alert-sql-server-management-studio"></a><span data-ttu-id="8710b-102">Define the Response to an Alert (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8710b-102">Define the Response to an Alert (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8710b-103">Este tópico descreve como definir como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responde a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8710b-103">This topic describes how to define how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responds to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8710b-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8710b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8710b-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8710b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8710b-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8710b-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8710b-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="8710b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8710b-108">**Para definir uma resposta a um alerta, usando:**</span><span class="sxs-lookup"><span data-stu-id="8710b-108">**To define the response to an alert, using:**</span></span>  
  
     [<span data-ttu-id="8710b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8710b-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8710b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8710b-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8710b-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8710b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8710b-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8710b-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8710b-113">As opções Pager e **net send** serão removidas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma versão futura do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8710b-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8710b-114">Evite usar esses recursos em novo trabalho de desenvolvimento e planeje modificar os aplicativos que os usam atualmente.</span><span class="sxs-lookup"><span data-stu-id="8710b-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="8710b-115">Observe que o SQL Server Agent deve ser configurado para usar o Database Mail a fim de enviar notificações por pager ou email a operadores.</span><span class="sxs-lookup"><span data-stu-id="8710b-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="8710b-116">Para obter mais informações, consulte [Atribuir alertas a um operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="8710b-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="8710b-117">gerencia trabalhos de forma fácil e com representação gráfica. Além disso, ele é recomendado para criar e gerenciar a infraestrutura de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="8710b-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8710b-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="8710b-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8710b-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="8710b-119">Permissions</span></span>  
 <span data-ttu-id="8710b-120">Somente membros da função de servidor fixa **sysadmin** podem definir a resposta a um alerta.</span><span class="sxs-lookup"><span data-stu-id="8710b-120">Only members of the **sysadmin** fixed server role can define the response to an alert.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8710b-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8710b-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="8710b-122">Para definir uma resposta a um alerta</span><span class="sxs-lookup"><span data-stu-id="8710b-122">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="8710b-123">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o alerta sobre o qual você quer definir uma resposta.</span><span class="sxs-lookup"><span data-stu-id="8710b-123">In **Object Explorer**, click the plus sign to expand the server that contains the alert on which you want to define a response.</span></span>  
  
2.  <span data-ttu-id="8710b-124">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="8710b-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="8710b-125">Clique no sinal de adição para expandir a pasta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="8710b-125">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="8710b-126">Clique com o botão direito do mouse no alerta no qual você deseja definir uma resposta e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8710b-126">Right-click the alert on which you want to define a response and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="8710b-127">Na caixa de diálogo Propriedades do _alert_name_**alerta** , em **selecionar uma página**, selecione **resposta**.</span><span class="sxs-lookup"><span data-stu-id="8710b-127">In the _alert_name_**alert properties** dialog box, under **Select a page**, select **Response**.</span></span>  
  
6.  <span data-ttu-id="8710b-128">Marque a caixa de seleção **Executar trabalho** e, na lista abaixo da caixa de seleção **Executar trabalho** , selecione um trabalho para executar quando o alerta ocorrer.</span><span class="sxs-lookup"><span data-stu-id="8710b-128">Select the **Execute job** check box and, from the list below the **Execute job** check box, select a job to execute when the alert occurs.</span></span> <span data-ttu-id="8710b-129">Você pode criar um trabalho novo clicando em **Novo Trabalho**</span><span class="sxs-lookup"><span data-stu-id="8710b-129">You can create a new job by clicking **New Job**.</span></span> <span data-ttu-id="8710b-130">Você pode exibir mais informações sobre o trabalho clicando em **Exibir Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="8710b-130">You can view more information about the job by clicking **View Job**.</span></span> <span data-ttu-id="8710b-131">Para obter mais informações sobre as opções disponíveis nas caixas de diálogo **novas** Propriedades de trabalho e **trabalho**_Job_name_ , consulte [criar um trabalho](create-a-job.md) e [exibir um trabalho](view-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="8710b-131">For more information about the available options in the **New Job** and **Job Properties**_job_name_ dialog boxes, see [Create a Job](create-a-job.md) and [View a Job](view-a-job.md).</span></span>  
  
7.  <span data-ttu-id="8710b-132">Marque a caixa de seleção **Notificar Operadores** se você quiser notificar os operadores quando o alerta for ativado.</span><span class="sxs-lookup"><span data-stu-id="8710b-132">Select the **Notify Operators** check box if you want to notify operators when the alert is activated.</span></span> <span data-ttu-id="8710b-133">Na **Lista de operadores**, selecione um ou mais dos métodos a seguir para notificar o operador ou operadores: **Email**, **Pager**ou **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="8710b-133">In the **Operator list**, select one or more of the following methods for notifying the operator or operators: **E-mail**, **Pager**, or **Net Send**.</span></span> <span data-ttu-id="8710b-134">Você pode criar um operador novo clicando em **Novo Operador**</span><span class="sxs-lookup"><span data-stu-id="8710b-134">You can create a new operator by clicking **New Operator**.</span></span> <span data-ttu-id="8710b-135">Você pode visualizar mais informações sobre um operador clicando em **Exibir Operador**.</span><span class="sxs-lookup"><span data-stu-id="8710b-135">You can view more information about an operator by clicking **View Operator**.</span></span> <span data-ttu-id="8710b-136">Para obter mais informações sobre as opções disponíveis nas caixas de diálogo **Novo Operador** e **Exibir Propriedades do Operador** , consulte [Create an Operator](create-an-operator.md) e [View Information About an Operator](view-information-about-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="8710b-136">For more information about the available options in the **New Operator** and **View Operator Properties** dialog boxes, see [Create an Operator](create-an-operator.md) and [View Information About an Operator](view-information-about-an-operator.md).</span></span>  
  
8.  <span data-ttu-id="8710b-137">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8710b-137">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8710b-138">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8710b-138">Using Transact-SQL</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="8710b-139">Para definir uma resposta a um alerta</span><span class="sxs-lookup"><span data-stu-id="8710b-139">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="8710b-140">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8710b-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8710b-141">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8710b-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8710b-142">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8710b-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for Test Alert.  
    -- assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="8710b-143">Para obter mais informações, consulte [sp_add_notification &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8710b-143">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
