---
title: Especificar um intervalo de dados de alteração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],specifying interval
ms.assetid: 17899078-8ba3-4f40-8769-e9837dc3ec60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 70b9c14d609f2db69ee5751eca18acb5262a07a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572130"
---
# <a name="specify-an-interval-of-change-data"></a><span data-ttu-id="48b8a-102">Especificar um intervalo de dados de alteração</span><span class="sxs-lookup"><span data-stu-id="48b8a-102">Specify an Interval of Change Data</span></span>
  <span data-ttu-id="48b8a-103">No fluxo de controle de um pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza uma carga incremental de dados de alteração, a primeira tarefa serve para calcular os pontos de extremidade do intervalo de alteração.</span><span class="sxs-lookup"><span data-stu-id="48b8a-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="48b8a-104">Estes pontos de extremidade são valores `datetime` e são armazenados em variáveis do pacote para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="48b8a-104">These endpoints are `datetime` values and will be stored in package variables for use later in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48b8a-105">Para obter uma descrição do processo geral de criação do fluxo de controle, consulte [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="48b8a-105">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="set-up-package-variables-for-the-endpoints"></a><span data-ttu-id="48b8a-106">Definir Variáveis do Pacote para os pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="48b8a-106">Set Up Package Variables for the Endpoints</span></span>  
 <span data-ttu-id="48b8a-107">Antes de configurar a tarefa Execute SQL para calcular os pontos de extremidade, as variáveis do pacote que irão armazenar os pontos de extremidade devem ter sido definidas.</span><span class="sxs-lookup"><span data-stu-id="48b8a-107">Before configuring the Execute SQL task to calculate the endpoints, the package variables that will store the endpoints have to be defined.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="48b8a-108">Para definir as variáveis do pacote</span><span class="sxs-lookup"><span data-stu-id="48b8a-108">To set up package variables</span></span>  
  
1.  <span data-ttu-id="48b8a-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra um novo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48b8a-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="48b8a-110">Na janela **Variáveis** , criar as seguintes variáveis:</span><span class="sxs-lookup"><span data-stu-id="48b8a-110">In the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="48b8a-111">Crie uma variável com o tipo de dados `datetime` para guardar o ponto inicial para o intervalo.</span><span class="sxs-lookup"><span data-stu-id="48b8a-111">Create a variable with the `datetime` data type to hold the starting point for the interval.</span></span>  
  
         <span data-ttu-id="48b8a-112">Este exemplo usa o nome de variável, ExtractStartTime.</span><span class="sxs-lookup"><span data-stu-id="48b8a-112">This example uses the variable name, ExtractStartTime.</span></span>  
  
    2.  <span data-ttu-id="48b8a-113">Crie outra variável com o tipo de dados `datetime` para guardar o ponto final para o intervalo.</span><span class="sxs-lookup"><span data-stu-id="48b8a-113">Create another variable with the `datetime` data type to hold the ending point for the interval.</span></span>  
  
         <span data-ttu-id="48b8a-114">Este exemplo usa o nome de variável, ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="48b8a-114">This example uses the variable name, ExtractEndTime.</span></span>  
  
 <span data-ttu-id="48b8a-115">Ao se calcular os pontos de extremidade em um pacote mestre que executa vários pacotes filho, é possível usar as configurações de Variável de Pacote Pai para passar os valores destas variáveis para cada pacote filho.</span><span class="sxs-lookup"><span data-stu-id="48b8a-115">If you calculate the endpoints in a master package that executes multiple child packages, you can use Parent Package Variable configurations to pass the values of these variables to each child package.</span></span> <span data-ttu-id="48b8a-116">Para obter mais informações, consulte [Tarefa Executar Pacote](../control-flow/execute-package-task.md) e [Usar os valores de variáveis e parâmetros em um pacote filho](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="48b8a-116">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
## <a name="calculate-a-starting-point-and-an-ending-point-for-change-data"></a><span data-ttu-id="48b8a-117">Calcule um Ponto Inicial e um Ponto Final para Dados de Alteração</span><span class="sxs-lookup"><span data-stu-id="48b8a-117">Calculate a Starting Point and an Ending Point for Change Data</span></span>  
 <span data-ttu-id="48b8a-118">Depois de definir as variáveis do pacote para os pontos de extremidade do intervalo, é possível calcular os valores reais para esses pontos de extremidade e mapear esses valores para as variáveis correspondentes.</span><span class="sxs-lookup"><span data-stu-id="48b8a-118">After you set up the package variables for the interval endpoints, you can calculate the actual values for those endpoints and map those values to the corresponding package variables.</span></span> <span data-ttu-id="48b8a-119">Devido a esses pontos de extremidade serem valores `datetime`, deve-se usar funções que podem calcular ou trabalhar com valores `datetime`.</span><span class="sxs-lookup"><span data-stu-id="48b8a-119">Because those endpoints are `datetime` values, you will have to use functions that can calculate or work with `datetime` values.</span></span> <span data-ttu-id="48b8a-120">A linguagem de expressão [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e a Transact-SQL têm funções que trabalham com valores `datetime`:</span><span class="sxs-lookup"><span data-stu-id="48b8a-120">Both the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language and Transact-SQL have functions that work with `datetime` values:</span></span>  
  
 <span data-ttu-id="48b8a-121">Funções na linguagem de expressão [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que trabalham com valores `datetime`</span><span class="sxs-lookup"><span data-stu-id="48b8a-121">Functions in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language that work with `datetime` values</span></span>  
 -   [<span data-ttu-id="48b8a-122">DATEADD &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-122">DATEADD &#40;SSIS Expression&#41;</span></span>](../expressions/dateadd-ssis-expression.md)  
  
-   [<span data-ttu-id="48b8a-123">DATEDIFF &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-123">DATEDIFF &#40;SSIS Expression&#41;</span></span>](../expressions/datediff-ssis-expression.md)  
  
-   [<span data-ttu-id="48b8a-124">DATEPART &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-124">DATEPART &#40;SSIS Expression&#41;</span></span>](../expressions/datepart-ssis-expression.md)  
  
-   [<span data-ttu-id="48b8a-125">DAY &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-125">DAY &#40;SSIS Expression&#41;</span></span>](../expressions/day-ssis-expression.md)  
  
-   [<span data-ttu-id="48b8a-126">GETDATE &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-126">GETDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getdate-ssis-expression.md)  
  
-   [<span data-ttu-id="48b8a-127">GETUTCDATE &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-127">GETUTCDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getutcdate-ssis-expression.md)  
  
-   [<span data-ttu-id="48b8a-128">MONTH &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-128">MONTH &#40;SSIS Expression&#41;</span></span>](../expressions/month-ssis-expression.md)  
  
-   [<span data-ttu-id="48b8a-129">YEAR &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="48b8a-129">YEAR &#40;SSIS Expression&#41;</span></span>](../expressions/year-ssis-expression.md)  
  
 <span data-ttu-id="48b8a-130">Funções em Transact-SQL que trabalham com valores `datetime`</span><span class="sxs-lookup"><span data-stu-id="48b8a-130">Functions in Transact-SQL that work with `datetime` values</span></span>  
 <span data-ttu-id="48b8a-131">[Tipos de dados e funções de data e hora&#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48b8a-131">[Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
 <span data-ttu-id="48b8a-132">Antes de usar uma destas funções `datetime` para calcular os pontos de extremidade, deve-se determinar se o intervalo é fixo e se ocorre regularmente.</span><span class="sxs-lookup"><span data-stu-id="48b8a-132">Before you use any one of these `datetime` functions to calculate the endpoints, you have to determine whether the interval is fixed and occurs on a regular schedule.</span></span> <span data-ttu-id="48b8a-133">Normalmente, você quer aplicar alterações que aconteceram em tabelas fonte para tabelas destino em um período regular.</span><span class="sxs-lookup"><span data-stu-id="48b8a-133">Typically, you want to apply changes that have occurred in source tables to destination tables on a regular schedule.</span></span> <span data-ttu-id="48b8a-134">Por exemplo, você poderia querer aplicar essas alterações de hora em hora, diariamente, ou semanalmente.</span><span class="sxs-lookup"><span data-stu-id="48b8a-134">For example, you might want to apply those changes on an hourly, daily, or weekly basis.</span></span>  
  
 <span data-ttu-id="48b8a-135">Depois que você entender se seu intervalo de alteração é fixo ou é mais aleatório, você pode calcular os pontos de extremidade:</span><span class="sxs-lookup"><span data-stu-id="48b8a-135">After you understand whether your change interval is fixed or is more random, you can calculate the endpoints:</span></span>  
  
-   <span data-ttu-id="48b8a-136">**Calculando a data e hora inicial**.</span><span class="sxs-lookup"><span data-stu-id="48b8a-136">**Calculating the starting date and time**.</span></span> <span data-ttu-id="48b8a-137">Usar a data e hora final da carga anterior como a data e hora inicial atual.</span><span class="sxs-lookup"><span data-stu-id="48b8a-137">You use the ending date and time from the previous load as the current starting date and time.</span></span> <span data-ttu-id="48b8a-138">Se você usar um intervalo fixo para cargas incrementais, calcule este valor usando as funções `datetime` da Transact-SQL ou da linguagem de expressão [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48b8a-138">If you use a fixed interval for incremental loads, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span> <span data-ttu-id="48b8a-139">Caso contrário, talvez seja preciso manter os pontos de extremidade entre execuções e usar uma tarefa Execute SQL ou uma tarefa Script para carregar o ponto de extremidade anterior.</span><span class="sxs-lookup"><span data-stu-id="48b8a-139">Otherwise, you might have to persist the endpoints between executions, and use an Execute SQL task or a Script task to load the previous endpoint.</span></span>  
  
-   <span data-ttu-id="48b8a-140">**Calculando a data e hora final**.</span><span class="sxs-lookup"><span data-stu-id="48b8a-140">**Calculating the ending date and time**.</span></span> <span data-ttu-id="48b8a-141">Se você usar um intervalo fixo para cargas incrementais, calcule a data e hora final atual como um deslocamento da data e hora inicial.</span><span class="sxs-lookup"><span data-stu-id="48b8a-141">If you use a fixed interval for incremental loads, calculate the current ending date and time as an offset from the starting date and time.</span></span> <span data-ttu-id="48b8a-142">Novamente, você pode calcular esse valor usando as `datetime` funções do Transact-SQL ou da linguagem de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressão.</span><span class="sxs-lookup"><span data-stu-id="48b8a-142">Again, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span>  
  
 <span data-ttu-id="48b8a-143">No procedimento seguinte, o intervalo de alteração usa um intervalo fixo e assume que o pacote de carga incremental é executado diariamente sem exceção.</span><span class="sxs-lookup"><span data-stu-id="48b8a-143">In the following procedure, the change interval uses a fixed interval and assumes that the incremental load package is run daily without exception.</span></span> <span data-ttu-id="48b8a-144">Caso contrário, os dados de alteração para intervalos ausentes seriam perdidos.</span><span class="sxs-lookup"><span data-stu-id="48b8a-144">Otherwise, change data for missed intervals would be lost.</span></span> <span data-ttu-id="48b8a-145">O ponto inicial para o intervalo é meia-noite de anteontem, ou seja, entre 24 e 48 horas atrás.</span><span class="sxs-lookup"><span data-stu-id="48b8a-145">The starting point for the interval is midnight the day before yesterday, that is, between 24 and 48 hours ago.</span></span> <span data-ttu-id="48b8a-146">O ponto final para o intervalo é meia-noite de ontem, ou seja, a noite anterior, entre 0 e 24 horas atrás.</span><span class="sxs-lookup"><span data-stu-id="48b8a-146">The ending point for the interval is midnight yesterday, that is, the previous night, between 0 and 24 hours ago.</span></span>  
  
#### <a name="to-calculate-the-starting-point-and-ending-point-for-the-capture-interval"></a><span data-ttu-id="48b8a-147">Para calcular o ponto inicial e final para o intervalo de captura</span><span class="sxs-lookup"><span data-stu-id="48b8a-147">To calculate the starting point and ending point for the capture interval</span></span>  
  
1.  <span data-ttu-id="48b8a-148">Na guia **Fluxo de Controle** do Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , adicione uma tarefa Execute SQL ao pacote.</span><span class="sxs-lookup"><span data-stu-id="48b8a-148">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add an Execute SQL Task to the package.</span></span>  
  
2.  <span data-ttu-id="48b8a-149">Abra o **Editor da tarefa Execute SQL**e na página **Geral** do editor, selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="48b8a-149">Open the **Execute SQL Task Editor**, and on the **General** page of the editor, select the following options:</span></span>  
  
    1.  <span data-ttu-id="48b8a-150">Para **Conjunto de Resultados**, selecione **Linha simples**.</span><span class="sxs-lookup"><span data-stu-id="48b8a-150">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="48b8a-151">Configure uma conexão válida com o banco de dados fonte.</span><span class="sxs-lookup"><span data-stu-id="48b8a-151">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="48b8a-152">Para **SQLSourceType**, selecione **Entrada direta**.</span><span class="sxs-lookup"><span data-stu-id="48b8a-152">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="48b8a-153">Para **SQLStatement**, digite a seguinte instrução SQL:</span><span class="sxs-lookup"><span data-stu-id="48b8a-153">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        SELECT DATEADD(dd,0, DATEDIFF(dd,0,GETDATE()-1)) AS ExtractStartTime,  
          DATEADD(dd,0, DATEDIFF(dd,0,GETDATE())) AS ExtractEndTime  
  
        ```  
  
3.  <span data-ttu-id="48b8a-154">Na página **Conjunto de Resultados** do **Editor da tarefa Executar SQL**, mapeie o resultado de ExtractStartTime para a variável do pacote ExtractStartTime e o resultado de ExtractEndTime para a variável do pacote ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="48b8a-154">On the **Result Set** page of the **Execute SQL Task Editor**, map the ExtractStartTime result to the ExtractStartTime package variable, and map the ExtractEndTime result to the ExtractEndTime package variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48b8a-155">Quando você usa uma expressão para definir o valor de uma variável [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], a expressão é avaliada sempre que o valor da variável é acessado.</span><span class="sxs-lookup"><span data-stu-id="48b8a-155">When you use an expression to set the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, the expression is evaluated every time that the value of the variable is accessed.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="48b8a-156">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="48b8a-156">Next Step</span></span>  
 <span data-ttu-id="48b8a-157">Depois de calcular o ponto inicial e final para um intervalo de alterações, a próxima etapa é determinar se os dados de alteração estão prontos.</span><span class="sxs-lookup"><span data-stu-id="48b8a-157">After you calculate the starting point and ending point for a range of changes, the next step is to determine whether the change data is ready.</span></span>  
  
 <span data-ttu-id="48b8a-158">**Próximo tópico:** [Determinar se os dados de alterações estão protos](determine-whether-the-change-data-is-ready.md)</span><span class="sxs-lookup"><span data-stu-id="48b8a-158">**Next topic:** [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b8a-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48b8a-159">See Also</span></span>  
 <span data-ttu-id="48b8a-160">[Usar variáveis em pacotes](../use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="48b8a-160">[Use Variables in Packages](../use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="48b8a-161">[Expressões do SSIS &#40;Integration Services&#41;](../expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="48b8a-161">[Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="48b8a-162">[Tarefa Executar SQL](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="48b8a-162">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="48b8a-163">Tarefa Script</span><span class="sxs-lookup"><span data-stu-id="48b8a-163">Script Task</span></span>](../control-flow/script-task.md)  
  
  
