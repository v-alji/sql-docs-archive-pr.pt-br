---
title: Criar um alerta usando um nível de gravidade | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- severity levels [SQL Server]
- alerts [SQL Server], severity levels
ms.assetid: a1fd71bf-5bf9-4ce2-9a1d-032576a4a6e9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ee353129d60fe7fc8bed0eff279920d8d4ba640
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682070"
---
# <a name="create-an-alert-using-severity-level"></a><span data-ttu-id="ee7aa-102">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="ee7aa-102">Create an Alert Using Severity Level</span></span>
  <span data-ttu-id="ee7aa-103">Este tópico descreve como criar um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta do Agent que é gerado quando um evento de um nível de severidade específico ocorre no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee7aa-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when an event of a specific severity level occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ee7aa-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ee7aa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ee7aa-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ee7aa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ee7aa-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ee7aa-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ee7aa-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="ee7aa-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ee7aa-108">**Para criar um alerta usando um nível de severidade, usando:**</span><span class="sxs-lookup"><span data-stu-id="ee7aa-108">**To create an alert using severity level, using:**</span></span>  
  
     [<span data-ttu-id="ee7aa-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee7aa-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ee7aa-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee7aa-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee7aa-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ee7aa-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ee7aa-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ee7aa-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="ee7aa-113">fornece um modo gráfico e fácil para gerenciar o sistema de alertas inteiro e é recomendado para configurar uma infraestrutura de alerta.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="ee7aa-114">Eventos gerados com **xp_logevent** ocorrem no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="ee7aa-115">Portanto, **xp_logevent** não dispara um alerta a menos que o **@database_name** para o alerta seja **'mestre'** ou NULL.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="ee7aa-116">Níveis de severidade de 19 a 25 enviam uma mensagem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao log de aplicativos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e disparam um alerta.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-116">Severity levels from 19 through 25 send a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] message to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log and trigger an alert.</span></span> <span data-ttu-id="ee7aa-117">Eventos com níveis de severidade inferiores a 19 vão disparar alertas apenas se você tiver usado **sp_altermessage**, RAISERROR WITH LOG ou **xp_logevent** para obrigá-los a serem gravados no log de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-117">Events with severity levels less than 19 will trigger alerts only if you have used **sp_altermessage**, RAISERROR WITH LOG, or **xp_logevent** to force them to be written to the Windows application log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee7aa-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="ee7aa-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee7aa-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="ee7aa-119">Permissions</span></span>  
 <span data-ttu-id="ee7aa-120">Por padrão, somente membros da função de servidor fixa **sysadmin** podem executar **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-120">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ee7aa-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee7aa-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="ee7aa-122">Para criar um alerta usando um nível de severidade</span><span class="sxs-lookup"><span data-stu-id="ee7aa-122">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="ee7aa-123">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor no qual você deseja criar um alerta usando um nível de severidade.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-123">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using severity level.</span></span>  
  
2.  <span data-ttu-id="ee7aa-124">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="ee7aa-125">Clique com o botão direito do mouse em **Alertas** e selecione **Novo Alerta**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-125">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="ee7aa-126">Na caixa de diálogo **Novo Alerta** , na caixa **Nome** , digite um nome para esse alerta.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-126">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="ee7aa-127">Na lista **Tipo** , selecione **Alerta de evento do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
6.  <span data-ttu-id="ee7aa-128">Em **Definição de alerta de evento**, na lista **Nome do banco de dados** , selecione um banco de dados para restringir o alerta a um banco de dados específico.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
7.  <span data-ttu-id="ee7aa-129">Em **Os alertas serão gerados com base em**, clique em **Severidade** e selecione a severidade específica que gerará o alerta.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-129">Under **Alerts will be raised based on**, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
8.  <span data-ttu-id="ee7aa-130">Marque a caixa correspondente à caixa de seleção **Gerar alertas quando a mensagem contiver** para restringir o alerta a uma sequência de caracteres específica e digite uma palavra-chave ou uma cadeia de caracteres para o **Texto da mensagem**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-130">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="ee7aa-131">O número máximo de caracteres é 100.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-131">The maximum number of characters is 100.</span></span>  
  
9. <span data-ttu-id="ee7aa-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-132">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ee7aa-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee7aa-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="ee7aa-134">Para criar um alerta usando um nível de severidade</span><span class="sxs-lookup"><span data-stu-id="ee7aa-134">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="ee7aa-135">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee7aa-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee7aa-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ee7aa-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ee7aa-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an alert (Test Alert) that runs the Back up the AdventureWorks2012 Database job when fired   
    -- assumes that the message 55001 and the Back up the AdventureWorks2012 Database job already exist.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert',  
        @message_id = 55001,   
       @severity = 0,   
       @notification_message = N'Error 55001 has occurred. The database will be backed up...',   
       @job_name = N'Back up the AdventureWorks2012 Database' ;  
    GO  
    ```  
  
 <span data-ttu-id="ee7aa-138">Para obter mais informações, consulte [sp_add_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ee7aa-138">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
