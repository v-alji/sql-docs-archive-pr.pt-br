---
title: Criar e testar uma função de classificador definida pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function create
- classifier function [SQL Server], test
- classifier function [SQL Server], create
- Resource Governor, classifier function test
ms.assetid: 7866b3c9-385b-40c6-aca5-32d3337032be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1b8e5371762e38cf2b3ac8c1d506b467dcfa7e3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680358"
---
# <a name="create-and-test-a-classifier-user-defined-function"></a><span data-ttu-id="8a105-102">Criar e testar uma função de classificação definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="8a105-102">Create and Test a Classifier User-Defined Function</span></span>
  <span data-ttu-id="8a105-103">Este tópico mostra como criar e testar uma função de classificador definida pelo usuário (UDF).</span><span class="sxs-lookup"><span data-stu-id="8a105-103">This topic shows how to create and test a classifier user-defined function (UDF).</span></span> <span data-ttu-id="8a105-104">As etapas envolvem a execução das instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] no Editor de Consultas [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8a105-104">The steps involve executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="8a105-105">O exemplo mostrado no procedimento a seguir ilustra as possibilidades para criar uma função de classificador definida pelo usuário bastante complexa.</span><span class="sxs-lookup"><span data-stu-id="8a105-105">The example shown in the following procedure illustrates the possibilities for creating a fairly complex classifier user-defined function.</span></span>  
  
 <span data-ttu-id="8a105-106">Em nosso exemplo:</span><span class="sxs-lookup"><span data-stu-id="8a105-106">In our example:</span></span>  
  
-   <span data-ttu-id="8a105-107">São criados um pool de recurso (pProductionProcessing) e grupo de carga de trabalho (gProductionProcessing) para processamento da produção durante um intervalo de hora especificado.</span><span class="sxs-lookup"><span data-stu-id="8a105-107">A resource pool (pProductionProcessing) and workload group (gProductionProcessing) are created for production processing during a specified time range.</span></span>  
  
-   <span data-ttu-id="8a105-108">Um pool de recursos (pOffHoursProcessing) e um grupo de carga de trabalho (gOffHoursProcessing) são criado para controlar as conexões que não atendem aos requisitos para processamento de produção.</span><span class="sxs-lookup"><span data-stu-id="8a105-108">A resource pool (pOffHoursProcessing) and workload group (gOffHoursProcessing) are created for handling connections that do not meet the requirements for production processing.</span></span>  
  
-   <span data-ttu-id="8a105-109">Uma tabela (TblClassificationTimeTable) é criada em mestre para manter as horas de início e término que podem ser avaliadas em relação à hora de logon.</span><span class="sxs-lookup"><span data-stu-id="8a105-109">A table (TblClassificationTimeTable) is created in master to hold start and end times that can be evaluated against a login time.</span></span> <span data-ttu-id="8a105-110">Isso deve ser criado em mestre porque o Governador de Recurso usa uma associação de esquema para funções de classificador.</span><span class="sxs-lookup"><span data-stu-id="8a105-110">This must be created in master because Resource Governor uses schema binding for classifier functions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8a105-111">Como uma prática recomendada, você não deve armazenar tabelas grandes, frequentemente atualizadas em mestre.</span><span class="sxs-lookup"><span data-stu-id="8a105-111">As a best practice, you should not store large, frequently updated tables in master.</span></span>  
  
 <span data-ttu-id="8a105-112">A função de classificador estende a hora de logon.</span><span class="sxs-lookup"><span data-stu-id="8a105-112">The classifier function extends the login time.</span></span> <span data-ttu-id="8a105-113">Uma função complexa pode fazer com que os logons alcancem o tempo limite ou reduzam a velocidade das conexões rápidas.</span><span class="sxs-lookup"><span data-stu-id="8a105-113">An overly complex function can cause logins to time out or slow down fast connections.</span></span>  
  
### <a name="to-create-the-classifier-user-defined-function"></a><span data-ttu-id="8a105-114">Para criar a função de classificador definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="8a105-114">To create the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="8a105-115">Crie e configure os novos pools de recurso e os grupos de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8a105-115">Create and configure the new resource pools and workload groups.</span></span> <span data-ttu-id="8a105-116">Atribua cada grupo de carga de trabalho ao pool de recurso apropriado.</span><span class="sxs-lookup"><span data-stu-id="8a105-116">Assign each workload group to the appropriate resource pool.</span></span>  
  
    ```  
    --- Create a resource pool for production processing  
    --- and set limits.  
    USE master  
    GO  
    CREATE RESOURCE POOL pProductionProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 100,  
         MIN_CPU_PERCENT = 50  
    )  
    GO  
    --- Create a workload group for production processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gProductionProcessing  
    WITH  
    (  
         IMPORTANCE = MEDIUM  
    )  
    --- Assign the workload group to the production processing  
    --- resource pool.  
    USING pProductionProcessing  
    GO  
    --- Create a resource pool for off-hours processing  
    --- and set limits.  
  
    CREATE RESOURCE POOL pOffHoursProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 50,  
         MIN_CPU_PERCENT = 0  
    )  
    GO  
    --- Create a workload group for off-hours processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gOffHoursProcessing  
    WITH  
    (  
         IMPORTANCE = LOW  
    )  
    --- Assign the workload group to the off-hours processing  
    --- resource pool.  
    USING pOffHoursProcessing  
    GO  
    ```  
  
2.  <span data-ttu-id="8a105-117">Atualize a configuração em-memória.</span><span class="sxs-lookup"><span data-stu-id="8a105-117">Update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
3.  <span data-ttu-id="8a105-118">Crie uma tabela e defina as horas de início e término para o intervalo de hora de processamento de produção.</span><span class="sxs-lookup"><span data-stu-id="8a105-118">Create a table and define the start and end times for the production processing time range.</span></span>  
  
    ```  
    USE master  
    GO  
    CREATE TABLE tblClassificationTimeTable  
    (  
         strGroupName     sysname          not null,  
         tStartTime       time              not null,  
         tEndTime         time              not null  
    )  
    GO  
    --- Add time values that the classifier will use to  
    --- determine the workload group for a session.  
    INSERT into tblClassificationTimeTable VALUES('gProductionProcessing', '6:35 AM', '6:15 PM')  
    go  
    ```  
  
4.  <span data-ttu-id="8a105-119">Crie a função de classificador que usa as funções e os valores de hora que podem ser avaliados em relação aos tempos na tabela de consulta.</span><span class="sxs-lookup"><span data-stu-id="8a105-119">Create the classifier function that uses time functions and values that can be evaluated against the times in the lookup table.</span></span> <span data-ttu-id="8a105-120">Para obter informações sobre como usar Tabelas de pesquisa em uma função de classificador, confira "Práticas recomendadas para usar Tabelas de pesquisa em uma função de classificador", neste tópico.</span><span class="sxs-lookup"><span data-stu-id="8a105-120">For information about using Lookup Tables in a classifier function, see "Best practices for using Lookup Tables in a classifier function" in this topic.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="8a105-121">introduziu um conjunto expandido de tipos e funções de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="8a105-121">introduced an expanded set of date and time data types and functions.</span></span> <span data-ttu-id="8a105-122">Para obter mais informações, veja [Tipos de dados e funções de data e hora &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a105-122">For more information, see [Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
    ```  
    CREATE FUNCTION fnTimeClassifier()  
    RETURNS sysname  
    WITH SCHEMABINDING  
    AS  
    BEGIN  
         DECLARE @strGroup sysname  
         DECLARE @loginTime time  
         SET @loginTime = CONVERT(time,GETDATE())  
         SELECT TOP 1 @strGroup = strGroupName  
              FROM dbo.tblClassificationTimeTable  
              WHERE tStartTime <= @loginTime and tEndTime >= @loginTime  
         IF(@strGroup is not null)  
         BEGIN  
              RETURN @strGroup  
         END  
    --- Use the default workload group if there is no match  
    --- on the lookup.  
         RETURN N'gOffHoursProcessing'  
    END  
    GO  
    ```  
  
5.  <span data-ttu-id="8a105-123">Registre a função de classificador e atualize a configuração em-memória.</span><span class="sxs-lookup"><span data-stu-id="8a105-123">Register the classifier function and update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR with (CLASSIFIER_FUNCTION = dbo.fnTimeClassifier)  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
### <a name="to-verify-the-resource-pools-workload-groups-and-the-classifier-user-defined-function"></a><span data-ttu-id="8a105-124">Para verificar os pools de recursos, os grupos de carga de trabalho e a função de classificador definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="8a105-124">To verify the resource pools, workload groups, and the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="8a105-125">Obtenha o pool de recurso e configuração do grupo de carga de trabalho usando a seguinte consulta.</span><span class="sxs-lookup"><span data-stu-id="8a105-125">Obtain the resource pool and workload group configuration by using the following query.</span></span>  
  
    ```  
    USE master  
    SELECT * FROM sys.resource_governor_resource_pools  
    SELECT * FROM sys.resource_governor_workload_groups  
    GO  
    ```  
  
2.  <span data-ttu-id="8a105-126">Verifique se a função de classificador existe e está habilitadas usando as consultas a seguir.</span><span class="sxs-lookup"><span data-stu-id="8a105-126">Verify that the classifier function exists and is enabled by using the following queries.</span></span>  
  
    ```  
    --- Get the classifier function Id and state (enabled).  
    SELECT * FROM sys.resource_governor_configuration  
    GO  
    --- Get the classifer function name and the name of the schema  
    --- that it is bound to.  
    SELECT   
          object_schema_name(classifier_function_id) AS [schema_name],  
          object_name(classifier_function_id) AS [function_name]  
    FROM sys.dm_resource_governor_configuration  
  
    ```  
  
3.  <span data-ttu-id="8a105-127">Obtenha os dados de runtime atuais para os pools de recurso e os grupos de carga de trabalho usando a seguinte consulta.</span><span class="sxs-lookup"><span data-stu-id="8a105-127">Obtain the current runtime data for the resource pools and workload groups by using the following query.</span></span>  
  
    ```  
    SELECT * FROM sys.dm_resource_governor_resource_pools  
    SELECT * FROM sys.dm_resource_governor_workload_groups  
    GO  
    ```  
  
4.  <span data-ttu-id="8a105-128">Descubra que sessões estão em cada grupo usando a seguinte consulta.</span><span class="sxs-lookup"><span data-stu-id="8a105-128">Find out what sessions are in each group by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, CAST(g.name as nvarchar(20)), s.session_id, s.login_time, CAST(s.host_name as nvarchar(20)), CAST(s.program_name AS nvarchar(20))  
              FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
              ON g.group_id = s.group_id  
    ORDER BY g.name  
    GO  
    ```  
  
5.  <span data-ttu-id="8a105-129">Descubra quais solicitações estão em cada grupo usando a seguinte consulta.</span><span class="sxs-lookup"><span data-stu-id="8a105-129">Find out which requests are in each group by using the following query.</span></span>  
  
    ```  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
                ON g.group_id = r.group_id  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
6.  <span data-ttu-id="8a105-130">Descubra que solicitações estão em execução no classificador usando a seguinte consulta.</span><span class="sxs-lookup"><span data-stu-id="8a105-130">Find out what requests are running in the classifier by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, g.name, s.session_id, s.login_time, s.host_name, s.program_name   
               FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = s.group_id  
                     AND 'preconnect' = s.status  
    ORDER BY g.name  
    GO  
  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = r.group_id  
                     AND 'preconnect' = r.status  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
### <a name="best-practices-for-using-lookup-tables-in-a-classifier-function"></a><span data-ttu-id="8a105-131">Práticas recomendadas para usar Tabelas de Pesquisa em uma função de classificação</span><span class="sxs-lookup"><span data-stu-id="8a105-131">Best practices for using Lookup Tables in a classifier function</span></span>  
  
1.  <span data-ttu-id="8a105-132">Não use uma tabela de pesquisa, a menos que seja absolutamente necessário.</span><span class="sxs-lookup"><span data-stu-id="8a105-132">Do not use a lookup table unless it is absolutely necessary.</span></span> <span data-ttu-id="8a105-133">Se precisar usar uma tabela de pesquisa, ela poderá ser embutida em código na própria função. No entanto, ela precisará ser equilibrada com as alterações dinâmicas e de complexidade da função de classificação.</span><span class="sxs-lookup"><span data-stu-id="8a105-133">If you need to use a lookup table, it can be hard coded into the function itself; however, this needs to be balanced with the complexity and dynamic changes of the classifier function.</span></span>  
  
2.  <span data-ttu-id="8a105-134">Limite a E/S executada para tabelas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8a105-134">Limit the I/O performed for lookup tables.</span></span>  
  
    1.  <span data-ttu-id="8a105-135">Use o TOP 1 para retornar apenas uma linha.</span><span class="sxs-lookup"><span data-stu-id="8a105-135">Use the TOP 1 to return only one row.</span></span>  
  
    2.  <span data-ttu-id="8a105-136">Minimize o número de linhas na tabela.</span><span class="sxs-lookup"><span data-stu-id="8a105-136">Minimize the number of rows in the table.</span></span>  
  
    3.  <span data-ttu-id="8a105-137">Faça com que todas as linhas da tabela fiquem em uma única página ou em um número pequeno de páginas.</span><span class="sxs-lookup"><span data-stu-id="8a105-137">Make all rows of the table exist on a single page, or a small number of pages.</span></span>  
  
    4.  <span data-ttu-id="8a105-138">Verifique se as linhas encontradas usando as operações Index Seek usam o maior número possível de colunas de busca.</span><span class="sxs-lookup"><span data-stu-id="8a105-138">Confirm that rows found using the Index Seek operations use as many seeking columns as possible.</span></span>  
  
    5.  <span data-ttu-id="8a105-139">Desnormalize para uma única tabela se estiver pensando em usar várias tabelas com junções.</span><span class="sxs-lookup"><span data-stu-id="8a105-139">De-normalize to a single table if you are considering using multiple tables with joins.</span></span>  
  
3.  <span data-ttu-id="8a105-140">Evite o bloqueio na tabela de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8a105-140">Prevent blocking on the lookup table.</span></span>  
  
    1.  <span data-ttu-id="8a105-141">Use a dica `NOLOCK` para evitar o bloqueio ou use `SET LOCK_TIMEOUT` na função com um valor máximo de 1000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="8a105-141">Use the `NOLOCK` hint to prevent blocking or use `SET LOCK_TIMEOUT` in the function with a maximum value of 1000 milliseconds.</span></span>  
  
    2.  <span data-ttu-id="8a105-142">As tabelas devem estar no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="8a105-142">Table(s) must exist in the master database.</span></span> <span data-ttu-id="8a105-143">(O banco de dados mestre é o único que tem a garantia de ser recuperado quando os computadores cliente tentam se conectar.)</span><span class="sxs-lookup"><span data-stu-id="8a105-143">(The master database is the only database that is guaranteed to be recovered when the client computers attempt to connect).</span></span>  
  
    3.  <span data-ttu-id="8a105-144">Sempre qualifique por completo o nome da tabela com o esquema.</span><span class="sxs-lookup"><span data-stu-id="8a105-144">Always fully-qualify the table name with the schema.</span></span> <span data-ttu-id="8a105-145">O nome do banco de dados não é necessário, uma vez que ele será o banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="8a105-145">The database name is not necessary since it has to be the master database.</span></span>  
  
    4.  <span data-ttu-id="8a105-146">Nenhum gatilho na tabela.</span><span class="sxs-lookup"><span data-stu-id="8a105-146">No triggers on the table.</span></span>  
  
    5.  <span data-ttu-id="8a105-147">Se você estiver atualizando o conteúdo da tabela, use uma transação no nível de isolamento do instantâneo para impedir que o Gravador bloqueie os Leitores.</span><span class="sxs-lookup"><span data-stu-id="8a105-147">If you are updating the table contents, make sure to use a snapshot isolation level transaction to prevent Writer blocking Readers.</span></span> <span data-ttu-id="8a105-148">Observe que o uso da dica `NOLOCK` também deve reduzir isso.</span><span class="sxs-lookup"><span data-stu-id="8a105-148">Note that using the `NOLOCK` hint should also mitigate this.</span></span>  
  
    6.  <span data-ttu-id="8a105-149">Se possível, desabilite a função de classificação ao alterar o conteúdo de tabela.</span><span class="sxs-lookup"><span data-stu-id="8a105-149">If possible, disable the classifier function when changing the table contents.</span></span>  
  
        > [!WARNING]  
        >  <span data-ttu-id="8a105-150">É altamente recomendável seguir essas práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="8a105-150">We highly recommend following these best practices.</span></span> <span data-ttu-id="8a105-151">Se houver problemas que o impeçam de seguir as práticas recomendadas, sugerimos que você contate o Suporte da Microsoft para evitar proativamente qualquer problema futuro.</span><span class="sxs-lookup"><span data-stu-id="8a105-151">If there are issues that prevent you from following the best practices, we recommend that you contact Microsoft Support so that you can proactively prevent any future problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a105-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a105-152">See Also</span></span>  
 <span data-ttu-id="8a105-153">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="8a105-153">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="8a105-154">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="8a105-154">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="8a105-155">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="8a105-155">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="8a105-156">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="8a105-156">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="8a105-157">[Configurar o administrador de recursos usando um modelo](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="8a105-157">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="8a105-158">[Exibir Propriedades do Administrador de Recursos](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8a105-158">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="8a105-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a105-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span></span>  
 <span data-ttu-id="8a105-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a105-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="8a105-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a105-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="8a105-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a105-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="8a105-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a105-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
