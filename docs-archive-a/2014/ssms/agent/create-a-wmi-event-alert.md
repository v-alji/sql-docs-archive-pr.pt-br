---
title: Criar um alerta de eventos WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI event alerts [SQL Server Management Studio]
ms.assetid: b8c46db6-408b-484e-98f0-a8af3e7ec763
author: stevestein
ms.author: sstein
ms.openlocfilehash: 737e7ccac9c92e663040e71339aa120f8db8b80b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575545"
---
# <a name="create-a-wmi-event-alert"></a><span data-ttu-id="158d2-102">Criar um alerta de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="158d2-102">Create a WMI Event Alert</span></span>
  <span data-ttu-id="158d2-103">Este tópico descreve como criar um alerta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a ser emitido mediante a ocorrência de um evento específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] monitorado pelo Provedor WMI para Eventos de Servidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158d2-103">This topic describes how to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] event occurs that is monitored by the WMI Provider for Server Events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="158d2-104">Para obter informações sobre como usar o provedor WMI para monitorar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eventos, consulte [provedor WMI para conceitos de eventos de servidor](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="158d2-104">For information about the using the WMI Provider to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, see [WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span></span> <span data-ttu-id="158d2-105">Para obter informações sobre as permissões necessárias para receber notificações de alertas de eventos WMI, consulte [Selecionar uma conta para o serviço do SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="158d2-105">For information about the permissions necessary to receive WMI event alert notifications, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span> <span data-ttu-id="158d2-106">Para obter mais informações sobre WQL, consulte [Usando o WQL com o Provedor WMI para eventos de servidor](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span><span class="sxs-lookup"><span data-stu-id="158d2-106">For more information about WQL, see [Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span></span>  
  
 <span data-ttu-id="158d2-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="158d2-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="158d2-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="158d2-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="158d2-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="158d2-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="158d2-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="158d2-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="158d2-111">**Para criar um alerta de eventos WMI, usando:**</span><span class="sxs-lookup"><span data-stu-id="158d2-111">**To create a WMI event alert, using:**</span></span>  
  
     [<span data-ttu-id="158d2-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="158d2-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="158d2-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="158d2-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="158d2-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="158d2-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="158d2-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="158d2-115">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="158d2-116">fornece um modo gráfico e fácil para gerenciar o sistema de alertas inteiro e é recomendado para configurar uma infraestrutura de alerta.</span><span class="sxs-lookup"><span data-stu-id="158d2-116">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="158d2-117">Eventos gerados com **xp_logevent** ocorrem no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="158d2-117">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="158d2-118">Portanto, **xp_logevent** não dispara um alerta a menos que o **@database_name** para o alerta seja **'mestre'** ou NULL.</span><span class="sxs-lookup"><span data-stu-id="158d2-118">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="158d2-119">Só têm suporte os namespaces WMI em computadores que executam o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="158d2-119">Only WMI namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="158d2-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="158d2-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="158d2-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="158d2-121">Permissions</span></span>  
 <span data-ttu-id="158d2-122">Por padrão, somente membros da função de servidor fixa **sysadmin** podem executar **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="158d2-122">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="158d2-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="158d2-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="158d2-124">Para criar um alerta de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="158d2-124">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="158d2-125">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor em que você deseja criar um alerta de eventos WMI.</span><span class="sxs-lookup"><span data-stu-id="158d2-125">In **Object Explorer,** click the plus sign to expand the server where you want to create a WMI event alert.</span></span>  
  
2.  <span data-ttu-id="158d2-126">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="158d2-126">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="158d2-127">Clique com o botão direito do mouse em **Alertas** e selecione **Novo Alerta**.</span><span class="sxs-lookup"><span data-stu-id="158d2-127">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="158d2-128">Na caixa de diálogo **Novo Alerta** , na caixa **Nome** , digite um nome para esse alerta.</span><span class="sxs-lookup"><span data-stu-id="158d2-128">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="158d2-129">Marque a caixa de seleção **Habilitar** para permitir a execução do alerta.</span><span class="sxs-lookup"><span data-stu-id="158d2-129">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="158d2-130">Por padrão, **Habilitar** encontra-se selecionado.</span><span class="sxs-lookup"><span data-stu-id="158d2-130">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="158d2-131">Na lista **Tipo** , selecione **Alerta de eventos WMI**.</span><span class="sxs-lookup"><span data-stu-id="158d2-131">In the **Type** list, select **WMI event alert**.</span></span>  
  
7.  <span data-ttu-id="158d2-132">Em **Definição de alerta do evento WMI**, na caixa **Namespace** , especifique o namespace WMI da instrução WQL que identifica o evento WMI que vai disparar o alerta.</span><span class="sxs-lookup"><span data-stu-id="158d2-132">Under **WMI event alert definition**, in the **Namespace** box, specify the WMI namespace for the WMI Query Language (WQL) statement that identifies which WMI event will trigger this alert.</span></span>  
  
8.  <span data-ttu-id="158d2-133">Na caixa **Consulta** , especifique a instrução WQL que identifica o evento ao qual o alerta responde.</span><span class="sxs-lookup"><span data-stu-id="158d2-133">In the **Query** box, specify the WQL statement that identifies the event that this alert responds to.</span></span>  
  
9. <span data-ttu-id="158d2-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="158d2-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="158d2-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="158d2-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="158d2-136">Para criar um alerta de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="158d2-136">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="158d2-137">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158d2-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="158d2-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="158d2-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="158d2-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="158d2-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a WMI event alert that retrieves all event properties for any ALTER_TABLE event that occurs on table AdventureWorks2012.Sales.SalesOrderDetail  
    -- This example assumes that the message 54001 already exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert 2',  
        @message_id = 54001  
        @notification_message = N'Error 54001 has occurred on the Sales.SalesOrderDetail table on the AdventureWorks2012 database. Please see the following information...',  
        @wmi_namespace = '\\.\root\Microsoft\SqlServer\ServerEvents\,  
        @wmi_query = N'SELECT * FROM ALTER_TABLE   
    WHERE DatabaseName = 'AdventureWorks2012' AND SchemaName = 'Sales'   
        AND ObjectType='Table' AND ObjectName = 'SalesOrderDetail'';  
    GO  
    ```  
  
 <span data-ttu-id="158d2-140">Para obter mais informações, consulte [sp_add_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="158d2-140">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
