---
title: Preparar para consultar os dados de alterações | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],preparing query
ms.assetid: 9ea2db7a-3dca-4bbf-9903-cccd2d494b5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ab732389d5a747c596472f14f5229361dd46275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569589"
---
# <a name="prepare-to-query-for-the-change-data"></a><span data-ttu-id="7ace9-102">Preparar para consultar os dados de alterações</span><span class="sxs-lookup"><span data-stu-id="7ace9-102">Prepare to Query for the Change Data</span></span>
  <span data-ttu-id="7ace9-103">No fluxo de controle de um pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza uma carga incremental de dados de alteração, a terceira e última tarefa servem para consultar as alterações dos dados e adicionar uma tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="7ace9-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to prepare to query for the change data and add a Data Flow task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ace9-104">A segunda tarefa para o fluxo de controle garante que os dados de alteração para o intervalo selecionado estarão prontos.</span><span class="sxs-lookup"><span data-stu-id="7ace9-104">The second task for the control flow is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="7ace9-105">Para obter mais informações sobre essa tarefa, consulte [Determinar se os dados de alteração estão prontos](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="7ace9-105">For more information about this task, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span> <span data-ttu-id="7ace9-106">Para obter uma descrição do processo geral de criação do fluxo de controle, consulte [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="7ace9-106">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations"></a><span data-ttu-id="7ace9-107">Considerações de criação</span><span class="sxs-lookup"><span data-stu-id="7ace9-107">Design Considerations</span></span>  
 <span data-ttu-id="7ace9-108">Para recuperar os dados de alteração, você chamará uma função com valor de tabela de Transact-SQL que aceita os pontos de extremidade do intervalo como parâmetros de entrada e retorna dados de alteração para o intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="7ace9-108">To retrieve the change data, you will call a Transact-SQL table-valued function that accepts the endpoints of the interval as input parameters and returns change data for the specified interval.</span></span> <span data-ttu-id="7ace9-109">Um componente de origem no fluxo de dados chama esta função.</span><span class="sxs-lookup"><span data-stu-id="7ace9-109">A source component in the data flow calls this function.</span></span> <span data-ttu-id="7ace9-110">Para obter informações sobre esse componente de origem, consulte [Recuperar e compreender os dados de alteração](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="7ace9-110">For information about this source component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
 <span data-ttu-id="7ace9-111">Os componentes de fonte do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usados com mais frequência, incluindo a fonte OLE DB, a fonte ADO e a fonte ADO NET, não podem derivar informações de parâmetros para uma função com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="7ace9-111">The most frequently used [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source components, including the OLE DB source, the ADO source, and the ADO NET source, cannot derive parameter information for a table-valued function.</span></span> <span data-ttu-id="7ace9-112">Entretanto, a maioria das fontes não pode chamar uma função parametrizada diretamente.</span><span class="sxs-lookup"><span data-stu-id="7ace9-112">Therefore, most sources cannot call a parameterized function directly.</span></span>  
  
 <span data-ttu-id="7ace9-113">Você tem duas opções de design para passar os parâmetros de entrada à função:</span><span class="sxs-lookup"><span data-stu-id="7ace9-113">You have two design options for passing the input parameters to the function:</span></span>  
  
-   <span data-ttu-id="7ace9-114">**Montar a consulta parametrizada como uma cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="7ace9-114">**Assemble the parameterized query as a string**.</span></span> <span data-ttu-id="7ace9-115">É possível usar uma tarefa Script ou uma tarefa Executar SQL para montar uma cadeia de caracteres de SQL dinâmica com valores de parâmetro codificados na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7ace9-115">You can use a Script task or an Execute SQL task to assemble a dynamic SQL string with parameter values hard-coded into the string.</span></span> <span data-ttu-id="7ace9-116">Em seguida, essa cadeia de caracteres poderá ser armazenada em uma variável do pacote e usada para definir a propriedade SqlCommand de um componente de origem.</span><span class="sxs-lookup"><span data-stu-id="7ace9-116">Then, you can store this string in a package variable and use it to set the SqlCommand property of a source component.</span></span> <span data-ttu-id="7ace9-117">Este procedimento é bem-sucedido porque o componente de origem não exige mais as informações do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7ace9-117">This approach succeeds because the source component no longer requires parameter information.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ace9-118">Um script pré-compilado causa menos sobrecarga do que uma tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="7ace9-118">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="7ace9-119">**Usar um wrapper parametrizado**.</span><span class="sxs-lookup"><span data-stu-id="7ace9-119">**Use a parameterized wrapper**.</span></span> <span data-ttu-id="7ace9-120">Se desejar, você poderá criar um procedimento armazenado parametrizado como um wrapper que chama a função com valor de tabela parametrizada.</span><span class="sxs-lookup"><span data-stu-id="7ace9-120">Alternatively, you can create a parameterized stored procedure as a wrapper that calls the parameterized table-valued function.</span></span> <span data-ttu-id="7ace9-121">Este procedimento é bem-sucedido porque o componente de origem pode derivar com êxito as informações de parâmetro para um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="7ace9-121">This approach succeeds because a source component can successfully derive parameter information for a stored procedure.</span></span>  
  
 <span data-ttu-id="7ace9-122">Este tópico usa a primeira opção de design e monta uma consulta parametrizada como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7ace9-122">This topic uses the first design option and assembles a parameterized query as a string.</span></span>  
  
## <a name="preparing-the-query"></a><span data-ttu-id="7ace9-123">Preparando a Consulta</span><span class="sxs-lookup"><span data-stu-id="7ace9-123">Preparing the Query</span></span>  
 <span data-ttu-id="7ace9-124">Antes de concatenar os valores dos parâmetros de entrada em uma cadeia de caracteres simples, é preciso configurar as variáveis do pacote que a consulta precisa.</span><span class="sxs-lookup"><span data-stu-id="7ace9-124">Before you can concatenate the values of the input parameters into a single query string, you have to set up the package variables that the query needs.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="7ace9-125">Para definir as variáveis do pacote</span><span class="sxs-lookup"><span data-stu-id="7ace9-125">To set up package variables</span></span>  
  
-   <span data-ttu-id="7ace9-126">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na janela **Variáveis** , crie uma variável com um tipo de dados String para manter a cadeia de caracteres de consulta que retorna da tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="7ace9-126">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create a variable with a string data type to hold the query string returned by the Execute SQL Task.</span></span>  
  
     <span data-ttu-id="7ace9-127">Este exemplo usa o nome da variável, SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="7ace9-127">This example uses the variable name, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="7ace9-128">Com a variável de pacote criada, você pode usar tanto uma tarefa Script quanto uma tarefa Executar SQL para concatenar os valores dos parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="7ace9-128">With the package variable created, you can use either a Script task or Execute SQL task to concatenate the values of the input parameters.</span></span> <span data-ttu-id="7ace9-129">Os dois procedimentos a seguir descrevem como configurar esses componentes.</span><span class="sxs-lookup"><span data-stu-id="7ace9-129">The following two procedures describe how to configure these components.</span></span>  
  
#### <a name="to-use-a-script-task-to-concatenate-the-query-string"></a><span data-ttu-id="7ace9-130">Usar uma tarefa Script para concatenar a cadeia de caracteres de consulta</span><span class="sxs-lookup"><span data-stu-id="7ace9-130">To use a Script task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="7ace9-131">Na guia **Fluxo de Controle** , adicione uma tarefa Script ao pacote após o contêiner Loop For e conecte o contêiner Loop For à tarefa.</span><span class="sxs-lookup"><span data-stu-id="7ace9-131">On the **Control Flow** tab, add a Script task to the package after the For Loop container and connect the For Loop container to the task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ace9-132">Este procedimento assume que o pacote executa uma carga incremental a partir de uma tabela simples.</span><span class="sxs-lookup"><span data-stu-id="7ace9-132">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="7ace9-133">Caso o pacote faça os carregamentos a partir de várias tabelas e tenha um pacote pai com vários pacotes filhos, a tarefa será adicionada como o primeiro componente para cada pacote filho.</span><span class="sxs-lookup"><span data-stu-id="7ace9-133">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="7ace9-134">Para obter mais informações, consulte [Executar uma carga incremental de várias tabelas](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7ace9-134">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="7ace9-135">No **Editor da Tarefa Script**, na página **Script** , selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7ace9-135">In the **Script Task Editor**, on the **Script** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="7ace9-136">Para **ReadOnlyVariables**, selecione **User::DataReady**, **User::ExtractStartTime**e **User::ExtractEndTime** .</span><span class="sxs-lookup"><span data-stu-id="7ace9-136">For **ReadOnlyVariables**, select **User::DataReady**, **User::ExtractStartTime**, and **User::ExtractEndTime** from the.</span></span>  
  
    2.  <span data-ttu-id="7ace9-137">Para **ReadWriteVariables**, selecione User::SqlDataQuery na lista.</span><span class="sxs-lookup"><span data-stu-id="7ace9-137">For **ReadWriteVariables**, select User::SqlDataQuery from the list.</span></span>  
  
3.  <span data-ttu-id="7ace9-138">No **Editor da Tarefa Script**, na página **Script** , clique em **Editar Script** para abrir o ambiente de desenvolvimento de script.</span><span class="sxs-lookup"><span data-stu-id="7ace9-138">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
4.  <span data-ttu-id="7ace9-139">No procedimento Principal, digite um dos seguintes segmentos de código:</span><span class="sxs-lookup"><span data-stu-id="7ace9-139">In the Main procedure, enter one of the following code segments:</span></span>  
  
    -   <span data-ttu-id="7ace9-140">Se você estiver programando em C#, digite as seguintes linhas de código:</span><span class="sxs-lookup"><span data-stu-id="7ace9-140">If you are programming in C#, enter the following lines of code:</span></span>  
  
        ```  
        int dataReady;  
        System.DateTime extractStartTime;  
        System.DateTime extractEndTime;  
        string sqlDataQuery;  
  
        dataReady = (int)Dts.Variables["DataReady"].Value;  
        extractStartTime = (System.DateTime)Dts.Variables["ExtractStartTime"].Value;  
        extractEndTime = (System.DateTime)Dts.Variables["ExtractEndTime"].Value;  
  
        if (dataReady == 2)  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) + "', '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
        else  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" + ", '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
  
        Dts.Variables["SqlDataQuery"].Value = sqlDataQuery;  
        ```  
  
         <span data-ttu-id="7ace9-141">\- ou –</span><span class="sxs-lookup"><span data-stu-id="7ace9-141">\- or -</span></span>  
  
    -   <span data-ttu-id="7ace9-142">Se você estiver programando em [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], digite as seguintes linhas de código:</span><span class="sxs-lookup"><span data-stu-id="7ace9-142">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following lines of code:</span></span>  
  
        ```  
        Dim dataReady As Integer  
        Dim extractStartTime As Date  
        Dim extractEndTime As Date  
        Dim sqlDataQuery As String  
  
        dataReady = CType(Dts.Variables("DataReady").Value, Integer)  
        extractStartTime = CType(Dts.Variables("ExtractStartTime").Value, Date)  
        extractEndTime = CType(Dts.Variables("ExtractEndTime").Value, Date)  
  
        If dataReady = 2 Then  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) & _  
              "', '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        Else  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" & _  
              ", '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        End If  
  
        Dts.Variables("SqlDataQuery").Value = sqlDataQuery  
  
        ```  
  
5.  <span data-ttu-id="7ace9-143">Tire a linha padrão de código que retorna `DtsExecResult.Success` da execução do script.</span><span class="sxs-lookup"><span data-stu-id="7ace9-143">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
6.  <span data-ttu-id="7ace9-144">Feche o ambiente de desenvolvimento de script e o **Editor da Tarefa Script**.</span><span class="sxs-lookup"><span data-stu-id="7ace9-144">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-use-an-execute-sql-task-to-concatenate-the-query-string"></a><span data-ttu-id="7ace9-145">Usar uma tarefa Executar SQL para concatenar a cadeia de caracteres de consulta</span><span class="sxs-lookup"><span data-stu-id="7ace9-145">To use an Execute SQL task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="7ace9-146">Na guia **Fluxo de Controle** , adicione uma tarefa Executar SQL ao pacote após o contêiner Loop For e conecte o contêiner Loop For à essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="7ace9-146">On the **Control Flow** tab, add an Execute SQL task to the package after the For Loop container and connect the For Loop container to this task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ace9-147">Este procedimento assume que o pacote executa uma carga incremental a partir de uma tabela simples.</span><span class="sxs-lookup"><span data-stu-id="7ace9-147">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="7ace9-148">Caso o pacote faça os carregamentos a partir de várias tabelas e tenha um pacote pai com vários pacotes filhos, a tarefa será adicionada como o primeiro componente para cada pacote filho.</span><span class="sxs-lookup"><span data-stu-id="7ace9-148">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="7ace9-149">Para obter mais informações, consulte [Executar uma carga incremental de várias tabelas](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7ace9-149">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="7ace9-150">No **Editor da Tarefa Executar SQL**, na página **Geral** , selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7ace9-150">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="7ace9-151">Para **Conjunto de Resultados**, selecione **Linha simples**.</span><span class="sxs-lookup"><span data-stu-id="7ace9-151">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="7ace9-152">Configure uma conexão válida com o banco de dados fonte.</span><span class="sxs-lookup"><span data-stu-id="7ace9-152">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="7ace9-153">Para **SQLSourceType**, selecione **Entrada direta**.</span><span class="sxs-lookup"><span data-stu-id="7ace9-153">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="7ace9-154">Para **SQLStatement**, digite a seguinte instrução SQL:</span><span class="sxs-lookup"><span data-stu-id="7ace9-154">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @ExtractStartTime datetime,  
        @ExtractEndTime datetime,   
        @DataReady int  
  
        select @DataReady = ?,   
        @ExtractStartTime = ?,   
        @ExtractEndTime = ?  
  
        if @DataReady = 2  
        select N'select * from CDCSample.uf_Customer'  
        + N'('''+ convert(nvarchar(30),@ExtractStartTime,120)  
        + ''', '''  
        + convert(nvarchar(30),@ExtractEndTime,120) + ''') '   
        as SqlDataQuery  
        else  
        select N'select * from CDCSample.uf_Customer'  
        + N'(null, '''  
        + convert(nvarchar(30),@ExtractEndTime,120)  
        + ''') '  
        as SqlDataQuery  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="7ace9-155">Neste exemplo, a cláusula `else` gera uma consulta para a carga inicial dos dados de alteração indicando um valor nulo para a data e hora de início.</span><span class="sxs-lookup"><span data-stu-id="7ace9-155">The `else` clause in this sample generates a query for the initial load of change data by passing a null value for the starting date and time.</span></span> <span data-ttu-id="7ace9-156">Este exemplo não indica o cenário em que as alterações realizadas antes da captura dos dados de alteração também tenham que ser carregadas para o Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="7ace9-156">This sample does not address the scenario in which changes that were made before change data capture was enabled also have to be uploaded to the data warehouse.</span></span>  
  
3.  <span data-ttu-id="7ace9-157">Na página **Mapeamento de Parâmetros** do **Editor de Tarefa Executar SQL**, faça o seguinte mapeamento:</span><span class="sxs-lookup"><span data-stu-id="7ace9-157">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, do the following mapping:</span></span>  
  
    1.  <span data-ttu-id="7ace9-158">Mapeie a variável DataReady para o parâmetro 0.</span><span class="sxs-lookup"><span data-stu-id="7ace9-158">Map the DataReady variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="7ace9-159">Mapeie a variável ExtractStartTime para o parâmetro 1.</span><span class="sxs-lookup"><span data-stu-id="7ace9-159">Map the ExtractStartTime variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="7ace9-160">Mapeie a variável ExtractEndTime para o parâmetro 2.</span><span class="sxs-lookup"><span data-stu-id="7ace9-160">Map the ExtractEndTime variable to parameter 2.</span></span>  
  
4.  <span data-ttu-id="7ace9-161">Na página **Conjunto de Resultados** do **Editor de Tarefa Executar SQL**, mapeie o Nome do Resultado para a variável SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="7ace9-161">On the **Result Set** page of the **Execute SQL Task Editor**, map the Result Name to the SqlDataQuery variable.</span></span>  
  
     <span data-ttu-id="7ace9-162">O Nome do Resultado é o nome da única coluna que é retornada, SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="7ace9-162">The Result Name is the name of the single column that is returned, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="7ace9-163">Os procedimentos anteriores configuram uma tarefa que prepara uma cadeia de caracteres de consulta com valores codificados da cadeia de caracteres para os parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="7ace9-163">The previous procedures configure a task that prepares a query string with hard-coded string values for the input parameters.</span></span> <span data-ttu-id="7ace9-164">O código a seguir é um exemplo de uma cadeia de caracteres de consulta:</span><span class="sxs-lookup"><span data-stu-id="7ace9-164">The following code is an example of such a query string:</span></span>  
  
 `select * from CDCSample. uf_Customer('2007-06-11 14:21:58', '2007-06-12 14:21:58')`  
  
## <a name="adding-a-data-flow-task"></a><span data-ttu-id="7ace9-165">Adicionando uma tarefa de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="7ace9-165">Adding a Data Flow Task</span></span>  
 <span data-ttu-id="7ace9-166">A última etapa que projeta o fluxo de controle para o pacote é adicionar uma tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="7ace9-166">The last step in designing the control flow for the package is to add a Data Flow task.</span></span>  
  
#### <a name="to-add-a-data-flow-task-and-complete-the-control-flow"></a><span data-ttu-id="7ace9-167">Adicionar uma tarefa de fluxo de dados e completar o fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="7ace9-167">To add a Data Flow task and complete the control flow</span></span>  
  
-   <span data-ttu-id="7ace9-168">Na guia **Fluxo de Controle** , adicione uma tarefa de fluxo de dados e conecte a tarefa que concatenou a cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="7ace9-168">On the **Control Flow** tab, add a Data Flow task and connect the task that concatenated the query string.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7ace9-169">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7ace9-169">Next Step</span></span>  
 <span data-ttu-id="7ace9-170">Depois de preparar a cadeia de caracteres de consulta e configurar a tarefa de fluxo de dados, a próxima etapa é criar a função com valor de tabela que irá recuperar os dados de alteração do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7ace9-170">After you prepare the query string and configure the Data Flow task, the next step is create the table-valued function that will retrieve the change data from the database.</span></span>  
  
 <span data-ttu-id="7ace9-171">**Próximo tópico:** [Criar a função para recuperar os dados de alteração](create-the-function-to-retrieve-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="7ace9-171">**Next topic:** [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md)</span></span>  
  
  
