---
title: Definir o fluxo de êxito ou falha das etapas do trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, action flow logic
- successful jobs [SQL Server]
- failed jobs [SQL Server]
- jobs [SQL Server Agent], action flow logic
ms.assetid: 23041ccf-8a07-41d3-85b9-c449a54b7e1e
author: stevestein
ms.author: sstein
ms.openlocfilehash: fddc5820676cb231b6f0cd5f7151e24d8eceaefa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686013"
---
# <a name="set-job-step-success-or-failure-flow"></a><span data-ttu-id="565be-102">Set Job Step Success or Failure Flow</span><span class="sxs-lookup"><span data-stu-id="565be-102">Set Job Step Success or Failure Flow</span></span>
  <span data-ttu-id="565be-103">Ao criar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent, você pode especificar a ação que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser tomada se ocorrer uma falha durante a execução do trabalho.</span><span class="sxs-lookup"><span data-stu-id="565be-103">When creating [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you can specify what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take if a failure occurs during job execution.</span></span> <span data-ttu-id="565be-104">Determine a ação a ser tomada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em caso de êxito ou falha de cada etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="565be-104">Determine the action that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take upon the success or failure of each job step.</span></span> <span data-ttu-id="565be-105">Use o procedimento a seguir para configurar a lógica do fluxo de ações da etapa de trabalho, usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="565be-105">Then use the following procedure to configure the job step action flow logic by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="565be-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="565be-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="565be-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="565be-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="565be-108">**Para definir o fluxo de êxito ou falha das etapas do trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="565be-108">**To set job step success or failure flow, using:**</span></span>  
  
     [<span data-ttu-id="565be-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="565be-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="565be-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="565be-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="565be-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="565be-111">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="565be-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="565be-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="565be-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="565be-113">Security</span></span>  
 <span data-ttu-id="565be-114">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="565be-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="565be-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="565be-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="565be-116">Para definir o fluxo da etapa de trabalho segundo o êxito ou falha</span><span class="sxs-lookup"><span data-stu-id="565be-116">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="565be-117">No **Pesquisador de Objetos**, expanda **SQL Server Agent**e, em seguida, expanda **Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="565be-117">In **Object Explorer**, expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
2.  <span data-ttu-id="565be-118">Clique com o botão direito do mouse no trabalho que deseja editar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="565be-118">Right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="565be-119">Selecione a página **Etapas** , clique em uma etapa e em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="565be-119">Select the **Steps** page, click a step, and then click **Edit**.</span></span>  
  
4.  <span data-ttu-id="565be-120">Na caixa de diálogo **Propriedades da Etapa de Trabalho** , selecione a página **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="565be-120">In the **Job Step Properties** dialog box, select the **Advanced** page.</span></span>  
  
5.  <span data-ttu-id="565be-121">Na caixa de diálogo **Ação ao obter êxito**, clique na ação a ser executada se a etapa de trabalho for concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="565be-121">In the **On success action**list, click the action to perform if the job step completes successfully.</span></span>  
  
6.  <span data-ttu-id="565be-122">Na caixa **Tentativas de repetição** , insira o número de vezes, de 0 a 9999, que a etapa de trabalho deve ser repetida antes de ser considerada como falha.</span><span class="sxs-lookup"><span data-stu-id="565be-122">In the **Retry attempts** box, enter the number of times from 0 through 9999 that the job step should be repeated before it is considered to have failed.</span></span> <span data-ttu-id="565be-123">Se você inserir um valor maior que 0 na caixa **Tentativas de repetição** , insira na caixa **Intervalo de repetição (minutos)** o número de minutos, de 1 a 9999, que devem decorrer antes de uma nova tentativa da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="565be-123">If you entered a value greater than 0 in the **Retry attempts** box, enter in the **Retry interval (minutes)** box the number of minutes from 1 through 9999 that must pass before the job step is retried.</span></span>  
  
7.  <span data-ttu-id="565be-124">Na lista **Ação ao falhar** , clique na ação a executar caso a etapa de trabalho falhe.</span><span class="sxs-lookup"><span data-stu-id="565be-124">In the **On failure action** list, click the action to perform if the job step fails.</span></span>  
  
8.  <span data-ttu-id="565be-125">Se o trabalho for um script [!INCLUDE[tsql](../../includes/tsql-md.md)] , você poderá escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="565be-125">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="565be-126">Na caixa **Arquivo de saída** , insira o nome de um arquivo de saída no qual o script deverá ser gravado.</span><span class="sxs-lookup"><span data-stu-id="565be-126">In the **Output file** box, enter the name of an output file to which the script output will be written.</span></span> <span data-ttu-id="565be-127">Por padrão, o arquivo é substituído sempre que a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="565be-127">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="565be-128">Se não quiser que o arquivo de saída seja substituído, marque **Anexar saída ao arquivo existente**.</span><span class="sxs-lookup"><span data-stu-id="565be-128">If you do not want the output file overwritten, check **Append output to existing file**.</span></span>  
  
    -   <span data-ttu-id="565be-129">Marque **Registrar na tabela** , se desejar registrar a etapa de trabalho em uma tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="565be-129">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="565be-130">Por padrão, o conteúdo da tabela é substituído sempre que a etapa de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="565be-130">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="565be-131">Se não quiser que o conteúdo da tabela seja substituído, marque **Anexar saída à entrada existente na tabela**.</span><span class="sxs-lookup"><span data-stu-id="565be-131">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="565be-132">Após a execução da etapa de trabalho, o conteúdo dessa tabela pode ser visualizado clicando-se em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="565be-132">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="565be-133">Marque **Incluir saída da etapa no histórico** , se desejar que a saída seja incluída no histórico da etapa.</span><span class="sxs-lookup"><span data-stu-id="565be-133">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="565be-134">A saída será exibida apenas se não houver erros.</span><span class="sxs-lookup"><span data-stu-id="565be-134">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="565be-135">A saída também pode ser truncada.</span><span class="sxs-lookup"><span data-stu-id="565be-135">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="565be-136">Se a lista **Executar como usuário** estiver disponível, selecione a conta proxy com as credenciais que o trabalho usará.</span><span class="sxs-lookup"><span data-stu-id="565be-136">If the **Run as user** list is available, select the proxy account with the credentials that the job will use.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="565be-137">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="565be-137">Using Transact-SQL</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="565be-138">Para definir o fluxo da etapa de trabalho segundo o êxito ou falha</span><span class="sxs-lookup"><span data-stu-id="565be-138">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="565be-139">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="565be-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="565be-140">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="565be-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="565be-141">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="565be-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @on_success_action = 1;  
    GO  
    ```  
  
 <span data-ttu-id="565be-142">Para obter mais informações, consulte [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="565be-142">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="565be-143">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="565be-143">Using SQL Server Management Objects</span></span>  

### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="565be-144">Para definir o fluxo da etapa de trabalho segundo o êxito ou falha</span><span class="sxs-lookup"><span data-stu-id="565be-144">To set job step success or failure flow</span></span>
  
 <span data-ttu-id="565be-145">Use a classe `JobStep` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="565be-145">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="565be-146">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="565be-146">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
