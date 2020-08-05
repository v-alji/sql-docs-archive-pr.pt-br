---
title: Criar um trabalho do SQL Server Agent para arquivar mensagens do Database Mail e logs de eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- archiving mail messages and attachments [SQL Server]
- removing mail messages and attachements
- Database Mail [SQL Server], archiving
- saving mail messages and attachments
ms.assetid: 8f8f0fba-f750-4533-9b76-a9cdbcdc3b14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b958b280c358a8aeb752600dee1c2aee31d14db1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572103"
---
# <a name="create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs"></a><span data-ttu-id="3011d-102">Criar um trabalho do SQL Server Agent para arquivar mensagens do Database Mail e logs de eventos</span><span class="sxs-lookup"><span data-stu-id="3011d-102">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>
  <span data-ttu-id="3011d-103">Cópias de mensagens do Database Mail e seus anexos são retidos em tabelas **msdb** junto com o log de eventos do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="3011d-103">Copies of Database Mail messages and their attachments are retained in **msdb** tables along with the Database Mail event log.</span></span> <span data-ttu-id="3011d-104">Periodicamente, convém reduzir o tamanho das tabelas e arquivar mensagens e eventos que não sejam mais necessários.</span><span class="sxs-lookup"><span data-stu-id="3011d-104">Periodically you might want to reduce the size of the tables and archive messages and events that are no longer needed.</span></span> <span data-ttu-id="3011d-105">Os procedimentos a seguir criam um trabalho do SQL Server Agent para automatizar o processo.</span><span class="sxs-lookup"><span data-stu-id="3011d-105">The following procedures create a SQL Server Agent job to automate the process.</span></span>  
  
-   <span data-ttu-id="3011d-106">**Antes de começar:**  , [Pré-requisitos](#Prerequisites), [Recomendações](#Recommendations), [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="3011d-106">**Before you begin:**  , [Prerequisites](#Prerequisites), [Recommendations](#Recommendations), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="3011d-107">**Para mensagens e logs do Archive Database Mail usando:**  [SQL Server Agent](#Process_Overview)</span><span class="sxs-lookup"><span data-stu-id="3011d-107">**To Archive Database Mail messages and logs using :**  [SQL Server Agent](#Process_Overview)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3011d-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3011d-108">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3011d-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3011d-109">Prerequisites</span></span>  
 <span data-ttu-id="3011d-110">As novas tabelas para armazenar os dados de arquivo morto devem estar localizadas em um banco de dados de arquivo morto especial.</span><span class="sxs-lookup"><span data-stu-id="3011d-110">The new tables to store the archive data might be located in a special archive database.</span></span> <span data-ttu-id="3011d-111">Alternativamente as linhas podem ser exportadas para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3011d-111">Alternatively the rows could be exported to a text file.</span></span>  
 
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3011d-112">Recomendações</span><span class="sxs-lookup"><span data-stu-id="3011d-112">Recommendations</span></span>  
 <span data-ttu-id="3011d-113">No seu ambiente de produção, convém adicionar outras verificações de erros e enviar uma mensagem de email aos operadores, caso o trabalho falhe.</span><span class="sxs-lookup"><span data-stu-id="3011d-113">In your production environment, you might want to add additional error checking and send an e-mail message to operators if the job fails.</span></span>  
  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3011d-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="3011d-114">Permissions</span></span>  
 <span data-ttu-id="3011d-115">É necessário ser membro da função de servidor fixa **sysadmin** para poder executar os procedimentos armazenados descritos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3011d-115">You must be a member of the **sysadmin** fixed server role to execute the stored procedures described in this topic.</span></span>  
  
  
###  <a name="overview-of-the-process"></a><a name="Process_Overview"></a> <span data-ttu-id="3011d-116">Visão geral do processo</span><span class="sxs-lookup"><span data-stu-id="3011d-116">Overview of the Process</span></span>  
  
-   <span data-ttu-id="3011d-117">O primeiro procedimento cria um trabalho denominado Archive Database Mail com as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3011d-117">The first procedure creates a job named Archive Database Mail with the following steps.</span></span>  
  
    1.  <span data-ttu-id="3011d-118">Copie todas as mensagens das tabelas do Database Mail em uma nova tabela nomeada com o mês anterior, no formato **DBMailArchive_** _<year_month>_ .</span><span class="sxs-lookup"><span data-stu-id="3011d-118">Copy all messages from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_**_<year_month>_.</span></span>  
  
    2.  <span data-ttu-id="3011d-119">Copie os anexos das mensagens copiadas na primeira etapa, das tabelas do Database Mail em uma nova tabela nomeada com o mês anterior, no formato **DBMailArchive_Attachments_** _<year_month>_ .</span><span class="sxs-lookup"><span data-stu-id="3011d-119">Copy the attachments related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Attachments_**_<year_month>_.</span></span>  
  
    3.  <span data-ttu-id="3011d-120">Copie os eventos do log de eventos do Database Mail referentes às mensagens copiadas na primeira etapa, das tabelas do Database Mail em uma nova tabela nomeada com o mês anterior, no formato **DBMailArchive_Log_** _<year_month>_ .</span><span class="sxs-lookup"><span data-stu-id="3011d-120">Copy the events from the Database Mail event log that are related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Log_**_<year_month>_.</span></span>  
  
    4.  <span data-ttu-id="3011d-121">Exclua os registros dos itens de correio transferidos das tabelas do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="3011d-121">Delete the records of the transferred mail items from the Database Mail tables.</span></span>  
  
    5.  <span data-ttu-id="3011d-122">Exclua os eventos referentes aos itens de correio transferidos do log de eventos do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="3011d-122">Delete the events related to the transferred mail items from the Database Mail event log.</span></span>  
  
-   <span data-ttu-id="3011d-123">Agende o trabalho a ser executado periodicamente.</span><span class="sxs-lookup"><span data-stu-id="3011d-123">Schedule the job to run periodically.</span></span>  
 
  
## <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="3011d-124">Para criar um trabalho do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3011d-124">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="3011d-125">No Pesquisador de Objetos, expanda o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, clique com o botão direito do mouse em **Trabalhos**e clique em **Novo Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="3011d-125">In Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, and then click **New Job**.</span></span>  
  
2.  <span data-ttu-id="3011d-126">Na caixa de diálogo **Novo Trabalho** , na caixa **Nome** , digite **Archive Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="3011d-126">In the **New Job** dialog box, in the **Name** box, type **Archive Database Mail**.</span></span>  
  
3.  <span data-ttu-id="3011d-127">Na caixa **Proprietário** , confirme que o proprietário é um membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3011d-127">In the **Owner** box, confirm that the owner is a member of the **sysadmin** fixed server role.</span></span>  
  
4.  <span data-ttu-id="3011d-128">Na caixa **Categoria** , clique em **Manutenção de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="3011d-128">In the **Category** box, click the **Database Maintenance**.</span></span>  
  
5.  <span data-ttu-id="3011d-129">Na caixa **Descrição** , digite **Archive Database Mail messages**e clique em **Etapas**.</span><span class="sxs-lookup"><span data-stu-id="3011d-129">In the **Description** box, type **Archive Database Mail messages**, and then click **Steps**.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-messages"></a><span data-ttu-id="3011d-130">Para criar uma etapa para arquivar as mensagens do Database Mail</span><span class="sxs-lookup"><span data-stu-id="3011d-130">To create a step to archive the Database Mail messages</span></span>  
  
1.  <span data-ttu-id="3011d-131">Na página **Etapas** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="3011d-131">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="3011d-132">Na caixa **Nome da etapa** , digite **Copy Database Mail Items**.</span><span class="sxs-lookup"><span data-stu-id="3011d-132">In the **Step name** box, type **Copy Database Mail Items**.</span></span>  
  
3.  <span data-ttu-id="3011d-133">Na caixa **Tipo** , selecione **Transact-SQL script (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="3011d-133">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="3011d-134">Na caixa **Banco de dados** , selecione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="3011d-134">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="3011d-135">Na caixa **Comando** , digite a seguinte instrução para criar uma tabela nomeada com o mês anterior, contendo linhas anteriores à data de início do mês atual:</span><span class="sxs-lookup"><span data-stu-id="3011d-135">In the **Command** box, type the following statement to create a table named after the previous month, containing rows older than the start of the current month:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_' + @LastMonth + '] FROM sysmail_allitems WHERE send_request_date < ''' + @CopyDate +'''';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="3011d-136">Clique em **OK** para salvar a etapa.</span><span class="sxs-lookup"><span data-stu-id="3011d-136">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-attachments"></a><span data-ttu-id="3011d-137">Para criar uma etapa para arquivar os anexos do Database Mail</span><span class="sxs-lookup"><span data-stu-id="3011d-137">To create a step to archive the Database Mail attachments</span></span>  
  
1.  <span data-ttu-id="3011d-138">Na página **Etapas** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="3011d-138">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="3011d-139">Na caixa **Nome da etapa** , digite **Copy Database Mail Attachments**.</span><span class="sxs-lookup"><span data-stu-id="3011d-139">In the **Step name** box, type **Copy Database Mail Attachments**.</span></span>  
  
3.  <span data-ttu-id="3011d-140">Na caixa **Tipo** , selecione **Transact-SQL script (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="3011d-140">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="3011d-141">Na caixa **Banco de dados** , selecione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="3011d-141">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="3011d-142">Na caixa **Comando** , digite a seguinte instrução para criar uma tabela de anexos nomeada com o mês anterior, contendo os anexos que correspondem às mensagens transferidas na etapa anterior:</span><span class="sxs-lookup"><span data-stu-id="3011d-142">In the **Command** box, type the following statement to create an attachments table named after the previous month, containing the attachments that correspond to the messages transferred in the previous step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Attachments_' + @LastMonth + '] FROM sysmail_attachments   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="3011d-143">Clique em **OK** para salvar a etapa.</span><span class="sxs-lookup"><span data-stu-id="3011d-143">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-log"></a><span data-ttu-id="3011d-144">Para criar uma etapa para arquivar o log do Database Mail</span><span class="sxs-lookup"><span data-stu-id="3011d-144">To create a step to archive the Database Mail log</span></span>  
  
1.  <span data-ttu-id="3011d-145">Na página **Etapas** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="3011d-145">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="3011d-146">Na caixa **Nome da etapa** , digite **Copy Database Mail Log**.</span><span class="sxs-lookup"><span data-stu-id="3011d-146">In the **Step name** box, type **Copy Database Mail Log**.</span></span>  
  
3.  <span data-ttu-id="3011d-147">Na caixa **Tipo** , selecione **Transact-SQL script (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="3011d-147">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="3011d-148">Na caixa **Banco de dados** , selecione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="3011d-148">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="3011d-149">Na caixa **Comando** , digite a seguinte instrução para criar uma tabela de log nomeada com o mês anterior, contendo as entradas do log que correspondem às mensagens transferidas na etapa anterior:</span><span class="sxs-lookup"><span data-stu-id="3011d-149">In the **Command** box, type the following statement to create a log table named after the previous month, containing the log entries that correspond to the messages transferred in the earlier step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Log_' + @LastMonth + '] FROM sysmail_Event_Log   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="3011d-150">Clique em **OK** para salvar a etapa.</span><span class="sxs-lookup"><span data-stu-id="3011d-150">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-rows-from-database-mail"></a><span data-ttu-id="3011d-151">Para criar uma etapa para remover as linhas arquivadas do Database Mail</span><span class="sxs-lookup"><span data-stu-id="3011d-151">To create a step to remove the archived rows from Database Mail</span></span>  
  
1.  <span data-ttu-id="3011d-152">Na página **Etapas** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="3011d-152">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="3011d-153">Na caixa **Nome da etapa** , digite **Remove rows from Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="3011d-153">In the **Step name** box, type **Remove rows from Database Mail**.</span></span>  
  
3.  <span data-ttu-id="3011d-154">Na caixa **Tipo** , selecione **Transact-SQL script (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="3011d-154">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="3011d-155">Na caixa **Banco de dados** , selecione **msdb**.</span><span class="sxs-lookup"><span data-stu-id="3011d-155">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="3011d-156">Na caixa **Comando** , digite a seguinte instrução para remover as linhas anteriores ao mês atual das tabelas do Database Mail:</span><span class="sxs-lookup"><span data-stu-id="3011d-156">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail tables:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_mailitems_sp @sent_before = @CopyDate ;  
    ```  
  
6.  <span data-ttu-id="3011d-157">Clique em **OK** para salvar a etapa.</span><span class="sxs-lookup"><span data-stu-id="3011d-157">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-items-from-database-mail-event-log"></a><span data-ttu-id="3011d-158">Para criar uma etapa para remover os itens arquivados do log de eventos do Database Mail</span><span class="sxs-lookup"><span data-stu-id="3011d-158">To create a step to remove the archived items from Database Mail event log</span></span>  
  
1.  <span data-ttu-id="3011d-159">Na página **Etapas** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="3011d-159">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="3011d-160">Na caixa **Nome da etapa** , digite **Remove rows from Database Mail event log**.</span><span class="sxs-lookup"><span data-stu-id="3011d-160">In the **Step Name** box type **Remove rows from Database Mail event log**.</span></span>  
  
3.  <span data-ttu-id="3011d-161">Na caixa **Tipo** , selecione **Transact-SQL script (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="3011d-161">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="3011d-162">Na caixa **Comando** , digite a seguinte instrução para remover as linhas anteriores ao mês atual do log de eventos do Database Mail:</span><span class="sxs-lookup"><span data-stu-id="3011d-162">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail event log:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_log_sp @logged_before = @CopyDate ;  
    ```  
  
5.  <span data-ttu-id="3011d-163">Clique em **OK** para salvar a etapa.</span><span class="sxs-lookup"><span data-stu-id="3011d-163">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-schedule-the-job-to-run-periodically"></a><span data-ttu-id="3011d-164">Para agendar o trabalho a ser executado periodicamente</span><span class="sxs-lookup"><span data-stu-id="3011d-164">To schedule the job to run periodically</span></span>  
  
1.  <span data-ttu-id="3011d-165">Na caixa de diálogo **Novo Trabalho** , clique em **Agendas**.</span><span class="sxs-lookup"><span data-stu-id="3011d-165">In the **New Job** dialog box, click **Schedules**.</span></span>  
  
2.  <span data-ttu-id="3011d-166">Na página **Agendas** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="3011d-166">On the **Schedules** page, click **New**.</span></span>  
  
3.  <span data-ttu-id="3011d-167">Na caixa **Nome** , digite **Archive Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="3011d-167">In the **Name** box, type **Archive Database Mail**.</span></span>  
  
4.  <span data-ttu-id="3011d-168">Na caixa **Tipo de agenda** , selecione **Recorrente**.</span><span class="sxs-lookup"><span data-stu-id="3011d-168">In the **Schedule type** box, select **Recurring**.</span></span>  
  
5.  <span data-ttu-id="3011d-169">Na área **Frequência** , selecione as opções para executar o trabalho periodicamente; por exemplo, uma vez por mês.</span><span class="sxs-lookup"><span data-stu-id="3011d-169">In the **Frequency** area, select the options to run the job periodically, for example once every month.</span></span>  
  
6.  <span data-ttu-id="3011d-170">Na área **Frequência diária**, selecione **Ocorre uma vez às \<time>** .</span><span class="sxs-lookup"><span data-stu-id="3011d-170">In the **Daily frequency** area, select **Occurs once at \<time>**.</span></span>  
  
7.  <span data-ttu-id="3011d-171">Verifique se as outras opções estão configuradas a seu gosto e clique em **OK** para salvar a agenda.</span><span class="sxs-lookup"><span data-stu-id="3011d-171">Verify that the other options are configured as you wish, and then click **OK** to save the schedule.</span></span>  
  
8.  <span data-ttu-id="3011d-172">Clique em **OK** para salvar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="3011d-172">Click **OK** to save the job.</span></span>  
  
  
  
  
