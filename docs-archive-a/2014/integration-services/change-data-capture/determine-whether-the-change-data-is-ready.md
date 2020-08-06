---
title: Determinar se os dados de alterações estão prontos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],determining readiness
ms.assetid: 04935f35-96cc-4d70-a250-0fd326f8daff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e672440938e366e53ba150f65d7bcd6aed8a58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684825"
---
# <a name="determine-whether-the-change-data-is-ready"></a><span data-ttu-id="4d6a8-102">Determinar se os dados de alteração estão prontos</span><span class="sxs-lookup"><span data-stu-id="4d6a8-102">Determine Whether the Change Data Is Ready</span></span>
  <span data-ttu-id="4d6a8-103">No fluxo de controle de um pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza uma carga incremental de dados de alteração, a segunda tarefa serve para garantir que os dados de alteração para o intervalo selecionado estejam prontos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the second task is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="4d6a8-104">Esta etapa é necessária, pois o processo de captura assíncrono pode ainda não ter processado todas as alterações até o ponto de extremidade selecionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-104">This step is necessary because the asynchronous capture process might not yet have processed all the changes up to the selected endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d6a8-105">A primeira tarefa para o fluxo de controle é calcular os pontos de extremidade do intervalo de alteração.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-105">The first task for the control flow is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="4d6a8-106">Para obter mais informações sobre essa tarefa, consulte [Especificar um intervalo de dados de alteração](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a8-106">For more information about this task, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span> <span data-ttu-id="4d6a8-107">Para obter uma descrição do processo geral de criação do fluxo de controle, consulte [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a8-107">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="understanding-the-components-of-the-solution"></a><span data-ttu-id="4d6a8-108">Compreendendo os componentes da solução</span><span class="sxs-lookup"><span data-stu-id="4d6a8-108">Understanding the Components of the Solution</span></span>  
 <span data-ttu-id="4d6a8-109">A solução descrita neste tópico usa quatro componentes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4d6a8-109">The solution described in this topic uses 4 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components:</span></span>  
  
-   <span data-ttu-id="4d6a8-110">Um contêiner do Loop For que avalia repetidamente a saída de uma Tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-110">A For Loop container that repeatedly evaluates the output of an Execute SQL Task.</span></span>  
  
-   <span data-ttu-id="4d6a8-111">Uma tarefa Executar SQL que consulta tabelas especiais mantidas pelo processo de captura dos dados de alteração e usa essas informações para determinar se os dados estão prontos ou não.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-111">An Execute SQL task that queries special tables that the change data capture process maintains and then uses this information to determine whether data is ready.</span></span>  
  
-   <span data-ttu-id="4d6a8-112">Um componente que implementa um atraso no processamento quando os dados não estão prontos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-112">A component that implements a delay in processing when the data is not ready.</span></span> <span data-ttu-id="4d6a8-113">Pode ser uma tarefa Script ou uma tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-113">This can be either a Script task or an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="4d6a8-114">Como opção, um componente que reporta um erro ou um tempo limite excedido quando a tarefa Executar SQL retorna um valor indicando um erro ou uma condição de tempo limite excedido.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-114">Optionally, a component that reports an error or a timeout when the Execute SQL task returns a value that indicates an error or a timeout condition.</span></span>  
  
 <span data-ttu-id="4d6a8-115">Esses componentes definem ou leem os valores de diversas variáveis de pacote para controlar o fluxo de execução dentro do loop e posteriormente no pacote.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-115">These components set or read the values of several package variables to control the flow of execution inside the loop and later in the package.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="4d6a8-116">Para definir as variáveis do pacote</span><span class="sxs-lookup"><span data-stu-id="4d6a8-116">To set up package variables</span></span>  
  
1.  <span data-ttu-id="4d6a8-117">Em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na janela **Variáveis** , crie as seguintes variáveis:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-118">Crie uma variável com um tipo de dados inteiros para manter o valor de status retornado pela tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-118">Create a variable with an integer data type to hold the status value returned by the Execute SQL task.</span></span>  
  
         <span data-ttu-id="4d6a8-119">Este exemplo usa o nome da variável, DataReady, com um valor inicial de 0.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-119">This example uses the variable name, DataReady, with an initial value of 0.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-120">Crie uma variável para segurar o período de tempo para atrasar quando os dados não estiverem prontos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-120">Create a variable to hold the period of time to delay when data is not ready.</span></span> <span data-ttu-id="4d6a8-121">Se você planeja usar uma tarefa Script para implementar o atraso, a variável deverá ter um tipo de dados inteiros.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-121">If you plan to use a Script task to implement the delay, the variable should have an integer data type integer.</span></span> <span data-ttu-id="4d6a8-122">Se você planeja usar uma tarefa Executar SQL com uma instrução WAITFOR, a variável deverá ter um tipo de dados de cadeia de caracteres para aceitar valores como "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="4d6a8-122">If you plan to use an Execute SQL task with a WAITFOR statement, the variable should have a string data type to accept values such as "00:00:10".</span></span>  
  
         <span data-ttu-id="4d6a8-123">Este exemplo usa o nome da variável, DelaySeconds, com um valor inicial de 10.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-123">This example uses the variable name, DelaySeconds, with an initial value of 10.</span></span>  
  
    3.  <span data-ttu-id="4d6a8-124">Crie uma variável com um tipo de dados inteiros para segurar a iteração atual do loop.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-124">Create a variable with an integer data type to hold the current iteration of the loop.</span></span>  
  
         <span data-ttu-id="4d6a8-125">Este exemplo usa o nome da variável, TimeoutCount, com um valor inicial de 0.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-125">This example uses the variable name, TimeoutCount, with an initial value of 0.</span></span>  
  
    4.  <span data-ttu-id="4d6a8-126">Crie uma variável com um tipo de dados inteiros, para especificar o número de vezes que o loop deve testar os dados antes de reportar uma condição de tempo limite excedido.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-126">Create a variable with an integer data type to specify the number of times that the loop should test for data before reporting a timeout condition.</span></span>  
  
         <span data-ttu-id="4d6a8-127">Este exemplo usa o nome da variável, TimeoutCeiling, com um valor inicial de 20.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-127">This example uses the variable name, TimeoutCeiling, with an initial value of 20.</span></span>  
  
    5.  <span data-ttu-id="4d6a8-128">(Opcional) Crie uma variável com um tipo de dados inteiros que possa ser usada para indicar a primeira carga de dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-128">(Optional) Create a variable with an integer data type that you can use to indicate the first load of change data.</span></span>  
  
         <span data-ttu-id="4d6a8-129">Este exemplo usa o nome da variável, IntervalID, e verifica apenas a existência de um valor 0 para indicar a carga inicial.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-129">This example uses the variable name, IntervalID, and checks only for a value of 0 to indicate the initial load.</span></span>  
  
## <a name="configuring-a-for-loop-container"></a><span data-ttu-id="4d6a8-130">Configurando um contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="4d6a8-130">Configuring a For Loop Container</span></span>  
 <span data-ttu-id="4d6a8-131">Com as variáveis definidas, o contêiner Loop For é o primeiro componente em ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-131">With the variables set, the For Loop container is the first component to be added.</span></span>  
  
#### <a name="to-configure-a-for-loop-container-to-wait-until-change-data-is-ready"></a><span data-ttu-id="4d6a8-132">Para configurar um contêiner Loop For espere até que dados de alteração estejam prontos</span><span class="sxs-lookup"><span data-stu-id="4d6a8-132">To configure a For Loop container to wait until change data is ready</span></span>  
  
1.  <span data-ttu-id="4d6a8-133">Na guia **Fluxo de Controle** do Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , adicione um contêiner Loop For ao fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-133">On the **Control Flow** tab of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a For Loop container to the control flow.</span></span>  
  
2.  <span data-ttu-id="4d6a8-134">Conecte a tarefa Executar SQL que calcula os pontos de extremidade do intervalo para o contêiner Loop For.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-134">Connect the Execute SQL Task that calculates the endpoints of the interval to the For Loop container.</span></span>  
  
3.  <span data-ttu-id="4d6a8-135">No **Editor do Loop For**, selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-135">In the **For Loop Editor**, select the following options:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-136">Para **InitExpression**, digite `@DataReady = 0`.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-136">For **InitExpression**, enter `@DataReady = 0`.</span></span>  
  
         <span data-ttu-id="4d6a8-137">Esta expressão define o valor inicial da variável de loop.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-137">This expression sets the initial value of the loop variable.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-138">Para **EvalExpression**m, digite `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-138">For **EvalExpression**m, enter `@DataReady == 0`.</span></span>  
  
         <span data-ttu-id="4d6a8-139">Quando esta expressão avaliar como **False**, a execução passará pelo loop e a carga incremental será iniciada.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-139">When this expression evaluates to **False**, execution passes out of the loop and the incremental load starts.</span></span>  
  
## <a name="configuring-the-execute-sql-task-that-queries-for-change-data"></a><span data-ttu-id="4d6a8-140">Configurando a tarefa Executar SQL que consulta a existência de dados de alteração</span><span class="sxs-lookup"><span data-stu-id="4d6a8-140">Configuring the Execute SQL Task That Queries for Change Data</span></span>  
 <span data-ttu-id="4d6a8-141">Dentro do contêiner Loop For, você adiciona uma tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-141">Inside the For Loop container, you add an Execute SQL task.</span></span> <span data-ttu-id="4d6a8-142">Esta tarefa consulta as tabelas que o processo de captura de dados de alteração mantém no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-142">This task queries the tables that the change data capture process maintains in the database.</span></span> <span data-ttu-id="4d6a8-143">O resultado desta consulta é um valor de status que indica se os dados de alteração estão prontos ou não.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-143">The result of this query is a status value that indicates whether the change data is ready.</span></span>  
  
 <span data-ttu-id="4d6a8-144">Na seguinte tabela, a primeira coluna mostra os valores retornados da tarefa Executar SQL pela consulta Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-144">In the following table, the first column shows the values returned from the Execute SQL task by the sample Transact-SQL query.</span></span> <span data-ttu-id="4d6a8-145">A segunda coluna mostra como os outros componentes respondem a estes valores.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-145">The second column shows how the other components respond to these values.</span></span>  
  
|<span data-ttu-id="4d6a8-146">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="4d6a8-146">Return Value</span></span>|<span data-ttu-id="4d6a8-147">Significado</span><span class="sxs-lookup"><span data-stu-id="4d6a8-147">Meaning</span></span>|<span data-ttu-id="4d6a8-148">Resposta</span><span class="sxs-lookup"><span data-stu-id="4d6a8-148">Response</span></span>|  
|------------------|-------------|--------------|  
|<span data-ttu-id="4d6a8-149">0</span><span class="sxs-lookup"><span data-stu-id="4d6a8-149">0</span></span>|<span data-ttu-id="4d6a8-150">Indica que os dados de alteração não estão prontos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-150">Indicates that the change data is not ready.</span></span><br /><br /> <span data-ttu-id="4d6a8-151">Não há nenhum registro de captura de dados de alteração posterior ao ponto final do intervalo selecionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-151">There are no change data capture records later than the ending point of the selected interval.</span></span>|<span data-ttu-id="4d6a8-152">A execução continua com o componente que implementa um atraso.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-152">Execution continues with the component that implements a delay.</span></span> <span data-ttu-id="4d6a8-153">Em seguida, o controle retorna para o contêiner Loop For, que continua a verificar a tarefa Executar SQL contanto que o valor retornado seja 0.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-153">Then control returns to the For Loop container, which continues to check the Execute SQL task as long as the value returned is 0.</span></span>|  
|<span data-ttu-id="4d6a8-154">1</span><span class="sxs-lookup"><span data-stu-id="4d6a8-154">1</span></span>|<span data-ttu-id="4d6a8-155">Pode indicar que os dados de alteração não foram capturados para o intervalo completo ou que foram excluídos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-155">Might indicate that the change data has not been captured for the complete interval, or that it has been deleted.</span></span> <span data-ttu-id="4d6a8-156">Isso é tratado como uma condição de erro.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-156">This is treated as an error condition.</span></span><br /><br /> <span data-ttu-id="4d6a8-157">Não há nenhum registro de captura de dados de alteração anterior ao ponto inicial do intervalo selecionado</span><span class="sxs-lookup"><span data-stu-id="4d6a8-157">There are no change data capture records earlier than the starting point of the selected interval</span></span>|<span data-ttu-id="4d6a8-158">A execução continua com o componente opcional que armazena o erro.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-158">Execution continues with the optional component that logs the error.</span></span>|  
|<span data-ttu-id="4d6a8-159">2</span><span class="sxs-lookup"><span data-stu-id="4d6a8-159">2</span></span>|<span data-ttu-id="4d6a8-160">Indica que os dados estão prontos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-160">Indicates that data is ready.</span></span><br /><br /> <span data-ttu-id="4d6a8-161">Não há nenhum registro de captura de dados de alteração anterior ao ponto inicial ou posterior ao ponto final do intervalo selecionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-161">There are change data capture records that are both earlier than the starting point and later than the ending point of the selected interval.</span></span>|<span data-ttu-id="4d6a8-162">A execução passa pelo contêiner Loop For e a carga incremental é iniciada.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-162">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="4d6a8-163">3</span><span class="sxs-lookup"><span data-stu-id="4d6a8-163">3</span></span>|<span data-ttu-id="4d6a8-164">Indica a carga inicial de todos os dados de alteração disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-164">Indicates the initial load of all available change data.</span></span><br /><br /> <span data-ttu-id="4d6a8-165">A lógica condicional obtém este valor de uma variável de pacote especial usada apenas para este propósito.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-165">The conditional logic obtains this value from a special package variable that is used only for this purpose.</span></span>|<span data-ttu-id="4d6a8-166">A execução passa pelo contêiner Loop For e a carga incremental é iniciada.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-166">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="4d6a8-167">5</span><span class="sxs-lookup"><span data-stu-id="4d6a8-167">5</span></span>|<span data-ttu-id="4d6a8-168">Indica que o TimeoutCeiling foi alcançado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-168">Indicates that the TimeoutCeiling has been reached.</span></span><br /><br /> <span data-ttu-id="4d6a8-169">O loop realizou um teste para obter os dados do número de vezes especificado e os dados ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-169">The loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="4d6a8-170">Sem este teste ou um teste semelhante, o pacote pode ser executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-170">Without this test or a similar test, the package might run indefinitely.</span></span>|<span data-ttu-id="4d6a8-171">A execução continua com o componente opcional que armazena o tempo limite excedido.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-171">Execution continues with the optional component that logs the timeout.</span></span>|  
  
#### <a name="to-configure-an-execute-sql-task-to-query-whether-change-data-is-ready"></a><span data-ttu-id="4d6a8-172">Para configurar uma tarefa Executar SQL para consultar se os dados de alteração estão prontos</span><span class="sxs-lookup"><span data-stu-id="4d6a8-172">To configure an Execute SQL task to query whether change data is ready</span></span>  
  
1.  <span data-ttu-id="4d6a8-173">Dentro do contêiner Loop For, adicione uma tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-173">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="4d6a8-174">No **Editor da Tarefa Executar SQL**, na página **Geral** , selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-174">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-175">Para **Conjunto de Resultados**, selecione **Linha simples**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-175">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-176">Configure uma conexão válida com o banco de dados fonte.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-176">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="4d6a8-177">Para **SQLSourceType**, selecione **Entrada direta**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-177">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="4d6a8-178">Para **SQLStatement**, digite a seguinte instrução SQL:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-178">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @DataReady int, @TimeoutCount int  
  
        if not exists (select tran_end_time from cdc.lsn_time_mapping  
                where tran_end_time > ?  )  
            select @DataReady = 0  
        else  
            if ? = 0  
                select @DataReady = 3   
        else  
            if not exists (select tran_end_time from cdc.lsn_time_mapping  
                    where tran_end_time <= ? )  
                select @DataReady = 1   
        else  
            select @DataReady = 2  
  
        select @TimeoutCount = ?  
        if (@DataReady = 0)  
            select @TimeoutCount = @TimeoutCount + 1  
        else  
            select @TimeoutCount = 0  
  
        if (@TimeoutCount > ?)  
            select @DataReady = 5  
  
        select @DataReady as DataReady, @TimeoutCount as TimeoutCount  
  
        ```  
  
3.  <span data-ttu-id="4d6a8-179">Na página **Mapeamentos de Parâmetros** do **Editor da Tarefa Executar SQL**, faça os seguintes mapeamentos:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-179">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, make the following mappings:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-180">Mapeie a variável ExtractEndTime para o parâmetro 0.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-180">Map the ExtractEndTime variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-181">Mapeie a variável IntervalID para o parâmetro 1.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-181">Map the IntervalID variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="4d6a8-182">Mapeie a variável ExtractStartTime para o parâmetro 2.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-182">Map the ExtractStartTime variable to parameter 2.</span></span>  
  
    4.  <span data-ttu-id="4d6a8-183">Mapeie a variável TimeoutCount para o parâmetro 3.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-183">Map the TimeoutCount variable to parameter 3.</span></span>  
  
    5.  <span data-ttu-id="4d6a8-184">Mapeie a variável TimeoutCeiling para o parâmetro 4.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-184">Map the TimeoutCeiling variable to parameter 4.</span></span>  
  
4.  <span data-ttu-id="4d6a8-185">Na página **Conjunto de Resultados** do **Editor da tarefa Executar SQL**, mapeie o resultado de DataReady para a variável DataReady e o resultado de TimeoutCount para a variável TimeoutCount.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-185">On the **Result Set** page of the **Execute SQL Task Editor**, map the DataReady result to the DataReady variable, and the TimeoutCount result to the TimeoutCount variable.</span></span>  
  
## <a name="waiting-until-the-change-data-is-ready"></a><span data-ttu-id="4d6a8-186">Esperando até que os dados de alteração estejam prontos</span><span class="sxs-lookup"><span data-stu-id="4d6a8-186">Waiting Until the Change Data Is Ready</span></span>  
 <span data-ttu-id="4d6a8-187">É possível usar um dos diversos métodos para implementar um atraso quando os dados de alteração não estiverem prontos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-187">You can use one of several methods to implement a delay when the change data is not ready.</span></span> <span data-ttu-id="4d6a8-188">Os dois procedimentos a seguir ilustram como usar uma tarefa Script ou uma tarefa Executar SQL para implementar o atraso.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-188">The following two procedures illustrate how to use a Script task or an Execute SQL task to implement the delay.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d6a8-189">Um script pré-compilado causa menos sobrecarga do que uma tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-189">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-a-script-task"></a><span data-ttu-id="4d6a8-190">Para implementar um atraso usando uma tarefa Script</span><span class="sxs-lookup"><span data-stu-id="4d6a8-190">To implement a delay by using a Script task</span></span>  
  
1.  <span data-ttu-id="4d6a8-191">Dentro do contêiner Loop For, adicione uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-191">Inside the For Loop container, add a Script task.</span></span>  
  
2.  <span data-ttu-id="4d6a8-192">Conecte a tarefa Executar SQL que realiza a consulta para determinar se os dados de alteração estão prontos para a nova tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-192">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
3.  <span data-ttu-id="4d6a8-193">Para a restrição de precedência que conecta a tarefa Executar SQL à tarefa Script, abra o **Editor de Restrição de Precedência** e selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-193">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-194">Para **Operação de avaliação**, selecione **Expressão e Restrição**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-194">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-195">Para **Valor**, selecione **Êxito**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-195">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="4d6a8-196">O valor de restrição de **Êxito** se refere ao sucesso da tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-196">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="4d6a8-197">Neste caso, o sucesso da tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-197">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="4d6a8-198">Para **Expressão**, digite `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-198">For **Expression**, enter `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span></span>  
  
    4.  <span data-ttu-id="4d6a8-199">Selecione **E Lógico. Todas as restrições deverão avaliar como True**, se ainda não estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-199">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
4.  <span data-ttu-id="4d6a8-200">Em **Editor da Tarefa Script**, na página **Script** , para **ReadOnlyVariables**, selecione a variável de número inteiro **User::DelaySeconds** da lista.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-200">In the **Script Task Editor**, on the **Script** page, for **ReadOnlyVariables**, select the **User::DelaySeconds** integer variable from the list.</span></span>  
  
5.  <span data-ttu-id="4d6a8-201">No **Editor da Tarefa Script**, na página **Script** , clique em **Editar Script** para abrir o ambiente de desenvolvimento de script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-201">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="4d6a8-202">No procedimento Principal, digite uma das seguintes linhas de código:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-202">In the Main procedure, enter one of the following lines of code:</span></span>  
  
    -   <span data-ttu-id="4d6a8-203">Se você estiver programando em C#, digite a seguinte linha de código:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-203">If you are programming in C#, enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep((int)Dts.Variables["DelaySeconds"].Value * 1000);  
        ```  
  
         <span data-ttu-id="4d6a8-204">\- ou –</span><span class="sxs-lookup"><span data-stu-id="4d6a8-204">\- or -</span></span>  
  
    -   <span data-ttu-id="4d6a8-205">Se você estiver programando em [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], digite a seguinte linha de código:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-205">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep(Ctype(Dts.Variables("DelaySeconds").Value, Integer) * 1000)  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="4d6a8-206">O método `Thread.Sleep` espera um argumento especificado em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-206">The `Thread.Sleep` method expects an argument that is specified in milliseconds.</span></span>  
  
7.  <span data-ttu-id="4d6a8-207">Tire a linha padrão de código que retorna `DtsExecResult.Success` da execução do script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-207">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
8.  <span data-ttu-id="4d6a8-208">Feche o ambiente de desenvolvimento de script e o **Editor da Tarefa Script**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-208">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-an-execute-sql-task"></a><span data-ttu-id="4d6a8-209">Para implementar um atraso usando uma tarefa Executar SQL</span><span class="sxs-lookup"><span data-stu-id="4d6a8-209">To implement a delay by using an Execute SQL task</span></span>  
  
1.  <span data-ttu-id="4d6a8-210">Dentro do contêiner Loop For, adicione uma tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-210">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="4d6a8-211">Conecte a tarefa Executar SQL que realiza a consulta para determinar se os dados de alteração estão prontos para a nova tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-211">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Execute SQL task.</span></span>  
  
3.  <span data-ttu-id="4d6a8-212">Para a restrição de precedência que conecta as duas tarefas Executar SQL, abra o **Editor de Restrição de Precedência** e selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-212">For the precedence constraint that connects the two Execute SQL tasks, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-213">Para **Operação de avaliação**, selecione **Expressão e Restrição**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-213">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-214">Para **Valor**, selecione **Êxito**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-214">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="4d6a8-215">O valor de restrição de **Êxito** se refere ao êxito da tarefa Executar SQL anterior.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-215">The constraint value of **Success** refers to the success of the previous Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="4d6a8-216">Para **Expressão**, digite `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-216">For **Expression**, enter `@DataReady == 0`.</span></span>  
  
    4.  <span data-ttu-id="4d6a8-217">Selecione **E Lógico. Todas as restrições deverão avaliar como True**, se ainda não estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-217">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="4d6a8-218">Esta seleção requer que ambas as condições, a restrição e a expressão, sejam verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-218">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
4.  <span data-ttu-id="4d6a8-219">No **Editor da Tarefa Executar SQL**, na página **Geral** , selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-219">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-220">Para **Conjunto de Resultados**, selecione **Linha simples**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-220">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-221">Configure uma conexão válida com o banco de dados fonte.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-221">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="4d6a8-222">Para **SQLSourceType**, selecione **Entrada direta**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-222">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="4d6a8-223">Para **SQLStatement**, digite a seguinte instrução SQL:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-223">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        WAITFOR DELAY ?  
  
        ```  
  
5.  <span data-ttu-id="4d6a8-224">Na página **Mapeamento de Parâmetro** do editor, mapeie a variável de cadeia de caracteres DelaySeconds para o parâmetro 0.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-224">On the **Parameter Mapping** page of the editor, map the DelaySeconds string variable to parameter 0.</span></span>  
  
## <a name="handling-an-error-condition"></a><span data-ttu-id="4d6a8-225">Controlando uma condição de erro</span><span class="sxs-lookup"><span data-stu-id="4d6a8-225">Handling an Error Condition</span></span>  
 <span data-ttu-id="4d6a8-226">Como opção, é possível configurar um componente adicional dentro do loop para armazenar um erro ou uma condição de tempo limite excedido:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-226">You can optionally configure an additional component inside the loop to log an error or a timeout condition:</span></span>  
  
-   <span data-ttu-id="4d6a8-227">Este componente pode armazenar uma condição de erro quando o valor da variável DataReady for = 1.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-227">This component can log an error condition when the value of the DataReady variable = 1.</span></span> <span data-ttu-id="4d6a8-228">Este valor indica que não há dados de alteração disponíveis antes do início do intervalo selecionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-228">This value indicates that there is no available change data before the start of the selected interval.</span></span>  
  
-   <span data-ttu-id="4d6a8-229">Este componente também pode armazenar uma condição de tempo limite excedido quando o valor da variável TimeoutCeiling é alcançado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-229">This component can also log a timeout condition when the value of the TimeoutCeiling variable is reached.</span></span> <span data-ttu-id="4d6a8-230">Este valor indica que o loop realizou um teste para obter os dados do número de vezes especificado e os dados ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-230">This value indicates the loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="4d6a8-231">Sem este teste ou um teste semelhante, o pacote pode ser executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-231">Without this test or a similar test, the package might run indefinitely.</span></span>  
  
#### <a name="to-configure-an-optional-script-task-to-log-an-error-condition"></a><span data-ttu-id="4d6a8-232">Para configurar uma tarefa Script opcional para armazenar uma condição de erro</span><span class="sxs-lookup"><span data-stu-id="4d6a8-232">To configure an optional Script task to log an error condition</span></span>  
  
1.  <span data-ttu-id="4d6a8-233">Se quiser reportar o erro ou o tempo limite excedido gravando uma mensagem no log, configure o armazenamento em log para o pacote.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-233">If you want to report the error or timeout by writing a message to the log, configure logging for the package.</span></span> <span data-ttu-id="4d6a8-234">Para obter mais informações, consulte [Habilitar o log de pacote no SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a8-234">For more information, see [Enable Package Logging in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
2.  <span data-ttu-id="4d6a8-235">Dentro do contêiner Loop For, adicione uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-235">Inside the For Loop container, add a Script task.</span></span>  
  
3.  <span data-ttu-id="4d6a8-236">Conecte a tarefa Executar SQL que realiza a consulta para determinar se os dados de alteração estão prontos para a nova tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-236">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
4.  <span data-ttu-id="4d6a8-237">Para a restrição de precedência que conecta a tarefa Executar SQL à tarefa Script, abra o **Editor de Restrição de Precedência** e selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d6a8-237">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="4d6a8-238">Para **Operação de avaliação**, selecione **Expressão e Restrição**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-238">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="4d6a8-239">Para **Valor**, selecione **Êxito**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-239">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="4d6a8-240">O valor de restrição de **Êxito** se refere ao sucesso da tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-240">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="4d6a8-241">Neste caso, o sucesso da tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-241">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="4d6a8-242">Para **Expressão**, digite `@DataReady == 1 || @DataReady == 5`.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-242">For **Expression**, enter `@DataReady == 1 || @DataReady == 5`.</span></span>  
  
    4.  <span data-ttu-id="4d6a8-243">Selecione **E Lógico. Todas as restrições deverão avaliar como True**, se ainda não estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-243">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="4d6a8-244">Esta seleção requer que ambas as condições, a restrição e a expressão, sejam verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-244">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
5.  <span data-ttu-id="4d6a8-245">No **Editor da Tarefa Script**, na página **Script** do editor, para **ReadOnlyVariables**, selecione **User::DataReady** e **User::ExtractStartTime** da lista para disponibilizar seus valores para o script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-245">In the **Script Task Editor**, on the **Script** page of the editor, for **ReadOnlyVariables**, select **User::DataReady** and **User::ExtractStartTime** from the list to make their values available to the script.</span></span>  
  
     <span data-ttu-id="4d6a8-246">Se você quiser incluir informações de determinadas variáveis do sistema (por exemplo, System::PackageName) nas informações gravadas no log, selecione também as variáveis.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-246">If you want to include information from certain system variables (for example, System::PackageName) in the information that you write to the log, select those variables also.</span></span>  
  
6.  <span data-ttu-id="4d6a8-247">No **Editor da Tarefa Script**, na página **Script** , clique em **Editar Script** para abrir o ambiente de desenvolvimento de script.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-247">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
7.  <span data-ttu-id="4d6a8-248">No procedimento Principal, digite o código para armazenar um erro chamando o método `Dts.Log` ou acione um evento chamando um dos métodos da interface `Dts.Events`.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-248">In the Main procedure, enter code to log an error by calling the `Dts.Log` method, or to raise an event by calling one of the methods of the `Dts.Events` interface.</span></span> <span data-ttu-id="4d6a8-249">Informe o pacote do erro retornando `Dts.TaskResult = Dts.Results.Failure`.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-249">Inform the package of the error by returning `Dts.TaskResult = Dts.Results.Failure`.</span></span>  
  
     <span data-ttu-id="4d6a8-250">A seguinte amostra mostra como gravar uma mensagem no log.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-250">The following sample shows how to write a message to the log.</span></span> <span data-ttu-id="4d6a8-251">Para obter mais informações, consulte [Registrando a tarefa Script](../extending-packages-scripting/task/logging-in-the-script-task.md), [Gerando eventos na tarefa Script](../extending-packages-scripting/task/raising-events-in-the-script-task.md)e [Retornando resultados da tarefa Script](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a8-251">For more information, see [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md), and [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>  
  
    ```  
    ' User variables.  
    Dim dataReady As Integer = _  
      CType(Dts.Variables("DataReady").Value, Integer)  
    Dim extractStartTime As Date = _  
      CType(Dts.Variables("ExtractStartTime").Value, DateTime)  
  
    ' System variables.  
    Dim packageName As String = _  
      Dts.Variables("PackageName").Value.ToString()  
    Dim executionStartTime As Date = _  
      CType(Dts.Variables("StartTime").Value, DateTime)  
  
    Dim eventMessage As New System.Text.StringBuilder()  
  
    If dataReady = 1 OrElse dataReady = 5 Then  
  
      If dataReady = 1 Then  
        eventMessage.AppendLine("Start Time Error")  
      Else  
        eventMessage.AppendLine("Timeout Error")  
      End If  
  
      With eventMessage  
        .Append("The package ")  
        .Append(packageName)  
        .Append(" started at ")  
        .Append(executionStartTime.ToString())  
        .Append(" and ended at ")  
        .AppendLine(DateTime.Now().ToString())  
        If dataReady = 1 Then  
          .Append("The specified ExtractStartTime was ")  
          .AppendLine(extractStartTime.ToString())  
        End If  
      End With  
  
      System.Windows.Forms.MessageBox.Show(eventMessage.ToString())  
  
      Dts.Log(eventMessage.ToString(), 0, Nothing)  
  
      Dts.TaskResult = Dts.Results.Failure  
  
    Else  
  
      Dts.TaskResult = Dts.Results.Success  
  
    End If  
  
    ```  
  
8.  <span data-ttu-id="4d6a8-252">Feche o ambiente de desenvolvimento de script e o **Editor da Tarefa Script**.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-252">Close the script development environment and the **Script Task Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="4d6a8-253">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="4d6a8-253">Next Step</span></span>  
 <span data-ttu-id="4d6a8-254">Após determinar que os dados de alteração estão prontos, a próxima etapa será preparar para consultar os dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="4d6a8-254">After you determine that change data is ready, the next step is to prepare to query for the change data.</span></span>  
  
 <span data-ttu-id="4d6a8-255">**Próximo tópico:** [Preparar para consultar os dados de alterações](prepare-to-query-for-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="4d6a8-255">**Next topic:** [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md)</span></span>  
  
  
