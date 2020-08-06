---
title: Criar uma etapa de trabalho do Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [Analysis Services]
ms.assetid: 03d4bb86-514b-4a55-97b9-c2c0fa08b428
author: stevestein
ms.author: sstein
ms.openlocfilehash: ed0e63c22d4cad270bcb544b03decba269e4f43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680307"
---
# <a name="create-an-analysis-services-job-step"></a><span data-ttu-id="bfad4-102">Create an Analysis Services Job Step</span><span class="sxs-lookup"><span data-stu-id="bfad4-102">Create an Analysis Services Job Step</span></span>
  <span data-ttu-id="bfad4-103">Este tópico descreve como criar e definir etapas de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que executem comandos e consultas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)] ou o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="bfad4-103">This topic describes how to create and define [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services commands and queries by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="bfad4-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="bfad4-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bfad4-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="bfad4-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bfad4-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="bfad4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bfad4-107">**Para criar etapas de trabalho do SQL Server usando comandos e/ou consultas do Analysis Services com:**</span><span class="sxs-lookup"><span data-stu-id="bfad4-107">**To create a SQL Server job steps using Analysis Services commands and/or queries, with:**</span></span>  
  
     [<span data-ttu-id="bfad4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bfad4-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="bfad4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bfad4-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="bfad4-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="bfad4-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bfad4-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bfad4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bfad4-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="bfad4-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bfad4-113">Se a etapa de trabalho usar um comando do Analysis Services, a instrução de comando deverá ser o método **Execute** do XML for Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bfad4-113">If the job step uses an Analysis Services command, the command statement must be an XML for Analysis Services **Execute** method.</span></span> <span data-ttu-id="bfad4-114">A instrução não pode conter um envelope do protocolo SOAP completo nem o método **Discover** do XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="bfad4-114">The statement may not contain a complete Simple Object Access Protocol (SOAP) envelope or an XML for Analysis **Discover** method.</span></span> <span data-ttu-id="bfad4-115">Embora o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ofereça suporte a envelopes SOAP completos e ao método **Discover** , as etapas de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não oferecem.</span><span class="sxs-lookup"><span data-stu-id="bfad4-115">While [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] supports complete SOAP envelopes and the **Discover** method, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps do not.</span></span> <span data-ttu-id="bfad4-116">Para obter mais informações sobre o XML for Analysis Services, consulte [Visão geral do XMLA (XML for Analysis)](https://msdn.microsoft.com/library/ms187190.aspx).</span><span class="sxs-lookup"><span data-stu-id="bfad4-116">For more information about XML for Analysis Services, see [XML for Analysis Overview (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span></span>  
  
-   <span data-ttu-id="bfad4-117">Se a etapa de trabalho usar uma consulta do Analysis Services, a instrução de consulta deverá ser uma consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="bfad4-117">If the job step uses an Analysis Services query, the query statement must be a multidimensional expressions (MDX) query.</span></span> <span data-ttu-id="bfad4-118">Para obter mais informações sobre MDX, consulte [conceitos básicos de consulta mdx &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="bfad4-118">For more information about MDX, see [MDX Query Fundamentals &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bfad4-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="bfad4-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bfad4-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="bfad4-120">Permissions</span></span>  
  
-   <span data-ttu-id="bfad4-121">Para executar uma etapa de trabalho que use o subsistema Analysis Services, o usuário deve ser um membro da função de servidor fixa **sysadmin** ou ter acesso a uma conta proxy válida definida para usar esse subsistema.</span><span class="sxs-lookup"><span data-stu-id="bfad4-121">To run a job step that uses the Analysis Services subsystem, a user must be a member of the **sysadmin** fixed server role or have access to a valid proxy account defined to use this subsystem.</span></span> <span data-ttu-id="bfad4-122">Além disso, a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ou o proxy deve ser um administrador do Analysis Services e uma conta de domínio do Windows válida.</span><span class="sxs-lookup"><span data-stu-id="bfad4-122">In addition, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account or the proxy must be an Analysis Services administrator and a valid Windows domain account.</span></span>  
  
-   <span data-ttu-id="bfad4-123">Apenas membros da função de servidor fixa **sysadmin** podem gravar em arquivo a saída de uma etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfad4-123">Only members of the **sysadmin** fixed server role can write job step output to a file.</span></span> <span data-ttu-id="bfad4-124">Se a etapa de trabalho for executada por usuários membros da função de banco de dados **SQLAgentUserRole** no banco de dados **msdb** , a saída poderá ser gravada apenas em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="bfad4-124">If the job step is run by users who are members of the **SQLAgentUserRole** database role in the **msdb** database, then the output can be written only to a table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="bfad4-125">Agent grava a saída da etapa de trabalho na tabela **sysjobstepslog** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="bfad4-125">Agent writes job step output to the **sysjobstepslog** table in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="bfad4-126">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="bfad4-126">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="bfad4-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bfad4-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="bfad4-128">Para criar uma etapa de trabalho de comando do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="bfad4-128">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="bfad4-129">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="bfad4-129">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="bfad4-130">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-130">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="bfad4-131">Para obter mais informações sobre como criar um trabalho, consulte [Criar trabalhos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bfad4-131">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="bfad4-132">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-132">In the **Job Properties** dialog box, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="bfad4-133">Na caixa de diálogo **Nova Etapa de Trabalho** , digite um trabalho **Step name**(Nome da etapa).</span><span class="sxs-lookup"><span data-stu-id="bfad4-133">In the **New Job Step** dialog box, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="bfad4-134">Na lista **Tipo** , clique em **Comando do SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-134">In the **Type** list, click **SQL Server Analysis Services Command**.</span></span>  
  
6.  <span data-ttu-id="bfad4-135">Na lista **Executar como** , selecione um proxy que tenha sido definido para usar o subsistema Comando do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bfad4-135">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Command subsystem.</span></span> <span data-ttu-id="bfad4-136">Um usuário membro da função de servidor fixa **sysadmin** também pode selecionar **Conta de Serviço do SQL Agent** para executar essa etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfad4-136">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="bfad4-137">Selecione o **Servidor** onde a etapa de trabalho será executada ou digite o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="bfad4-137">Select the **Server** where the job step will run, or type the server name.</span></span>  
  
8.  <span data-ttu-id="bfad4-138">Na caixa **Comando** , digite a instrução a executar ou clique em **Abrir** para selecionar uma instrução.</span><span class="sxs-lookup"><span data-stu-id="bfad4-138">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="bfad4-139">Clique na página **Avançado** para definir opções para essa etapa de trabalho, como a ação que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve tomar em caso de êxito ou falha da etapa, quantas vezes a etapa deve ser tentada e onde deve ser gravada sua saída.</span><span class="sxs-lookup"><span data-stu-id="bfad4-139">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="bfad4-140">Para criar uma etapa de trabalho de consulta do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="bfad4-140">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="bfad4-141">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="bfad4-141">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="bfad4-142">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-142">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="bfad4-143">Para obter mais informações sobre como criar um trabalho, consulte [Criar trabalhos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bfad4-143">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="bfad4-144">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-144">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="bfad4-145">Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfad4-145">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="bfad4-146">Na lista **Tipo** , clique em **Consulta do SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-146">In the **Type** list, click **SQL Server Analysis Services Query**.</span></span>  
  
6.  <span data-ttu-id="bfad4-147">Na lista **Executar como** , selecione um proxy que tenha sido definido para usar o subsistema Consulta do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bfad4-147">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Query subsystem.</span></span> <span data-ttu-id="bfad4-148">Um usuário membro da função de servidor fixa **sysadmin** também pode selecionar **Conta de Serviço do SQL Agent** para executar essa etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfad4-148">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="bfad4-149">Selecione o **Servidor** e o **Banco de Dados** onde a etapa de trabalho será executada ou digite o nome do servidor ou do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bfad4-149">Select the **Server** and the **Database** where the job step will run, or type the server or database name.</span></span>  
  
8.  <span data-ttu-id="bfad4-150">Na caixa **Comando** , digite a instrução a executar ou clique em **Abrir** para selecionar uma instrução.</span><span class="sxs-lookup"><span data-stu-id="bfad4-150">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="bfad4-151">Clique na página **Avançado** para definir opções para essa etapa de trabalho, como a ação que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve tomar em caso de êxito ou falha da etapa, quantas vezes a etapa deve ser tentada e onde deve ser gravada sua saída.</span><span class="sxs-lookup"><span data-stu-id="bfad4-151">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="bfad4-152">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bfad4-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="bfad4-153">Para criar uma etapa de trabalho de comando do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="bfad4-153">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="bfad4-154">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfad4-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bfad4-155">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bfad4-156">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-156">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses XMLA to create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database ',  
        @subsystem = N'ANALYSISCOMMAND',  
        @command = N' <Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
        <ParentObject>  
            <DatabaseID>AdventureWorks2012</DatabaseID>  
        </ParentObject>  
        <ObjectDefinition>  
            <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
                <ID>AdventureWorks2012</ID>  
                <Name>Adventure Works 2012</Name>  
                <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorks2012;Integrated Security=True</ConnectionString>  
                <ImpersonationInfo>  
                    <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
                </ImpersonationInfo>  
                <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
                <Timeout>PT0S</Timeout>  
            </DataSource>  
        </ObjectDefinition>  
    </Create>', ;  
    GO  
    ```  
  
 <span data-ttu-id="bfad4-157">Para obter mais informações, consulte [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bfad4-157">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="bfad4-158">Para criar uma etapa de trabalho de consulta do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="bfad4-158">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="bfad4-159">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfad4-159">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bfad4-160">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-160">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bfad4-161">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="bfad4-161">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses MDX to return data  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Returns the Internet sales amount by state',  
        @subsystem = N'ANALYSISQUERY',  
        @command = N' SELECT  
       [Measures].[Internet Sales Amount] ON COLUMNS,  
       [Customer].[State-Province].Members ON ROWS  
    FROM [AdventureWorks2012]',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="bfad4-162">Para obter mais informações, consulte [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bfad4-162">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="bfad4-163">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="bfad4-163">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="bfad4-164">**Para criar uma etapa de trabalho de script PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bfad4-164">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="bfad4-165">Use a classe `JobStep` usando uma linguagem de programação que você escolher, como XMLA ou MDX.</span><span class="sxs-lookup"><span data-stu-id="bfad4-165">Use the `JobStep` class by using a programming language that you choose, such as XMLA or MDX.</span></span> <span data-ttu-id="bfad4-166">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="bfad4-166">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
