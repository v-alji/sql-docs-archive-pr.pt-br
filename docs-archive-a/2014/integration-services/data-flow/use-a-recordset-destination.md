---
title: Usar um destino do conjunto de registros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Recordset destination
ms.assetid: a7b143dc-8008-404f-83b0-b45ffbca6029
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34d1d5a7aa76876a9d8718b691b1d24a8835e2e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582021"
---
# <a name="use-a-recordset-destination"></a><span data-ttu-id="8e3f9-102">Usar um destino do conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="8e3f9-102">Use a Recordset Destination</span></span>
  <span data-ttu-id="8e3f9-103">O destino do Conjunto de Registros não salva dados em uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-103">The Recordset destination does not save data to an external data source.</span></span> <span data-ttu-id="8e3f9-104">Em vez disso, o destino do Conjunto de Registros salva dados na memória em um conjunto de registros armazenado em uma variável de pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do tipo de dados `Object`.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-104">Instead, the Recordset destination saves data in memory in a recordset that is stored in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package variable of the `Object` data type.</span></span> <span data-ttu-id="8e3f9-105">Depois que o destino do Conjunto de Registros salva os dados, geralmente você usa um contêiner Loop Foreach com o enumerador ADO Foreach para processar uma linha do conjunto de registros de cada vez.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-105">After the Recordset destination saves the data, you typically use a Foreach Loop container with the Foreach ADO enumerator to process one row of the recordset at a time.</span></span> <span data-ttu-id="8e3f9-106">O enumerador ADO Foreach salva o valor de cada coluna da linha atual em uma variável de pacote separada.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-106">The Foreach ADO enumerator saves the value from each column of the current row into a separate package variable.</span></span> <span data-ttu-id="8e3f9-107">Em seguida, as tarefas que você configura dentro do contêiner Loop Foreach leem esses valores das variáveis e executam alguma ação com eles.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-107">Then, the tasks that you configure inside the Foreach Loop container read those values from the variables and perform some action with them.</span></span>  
  
 <span data-ttu-id="8e3f9-108">Você pode usar o destino do Conjunto de Registros em muitos cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-108">You can use the Recordset destination in many different scenarios.</span></span> <span data-ttu-id="8e3f9-109">Estes são alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-109">Here are some examples:</span></span>  
  
-   <span data-ttu-id="8e3f9-110">É possível usar uma tarefa Enviar Email e a linguagem da expressão do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para enviar uma mensagem de email personalizada para cada linha no conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-110">You can use a Send Mail task and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language to send a customized e-mail message for each row in the recordset.</span></span>  
  
-   <span data-ttu-id="8e3f9-111">Você pode usar um componente Script configurado como fonte, dentro de uma tarefa de fluxo de dados, para ler os valores nas colunas do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-111">You can use a Script component configured as a source, inside a Data Flow task, to read the column values into the columns of the data flow.</span></span> <span data-ttu-id="8e3f9-112">Em seguida, é possível usar transformações e destinos para transformar e salvar a linha.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-112">Then, you can use transformations and destinations to transform and save the row.</span></span> <span data-ttu-id="8e3f9-113">Neste exemplo, a tarefa de fluxo de dados é executada uma vez para cada linha.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-113">In this example, the Data Flow task runs once for each row.</span></span>  
  
 <span data-ttu-id="8e3f9-114">As seções a seguir primeiro descrevem o processo geral de uso do destino do Conjunto de Registros e depois mostram um exemplo específico de como utilizar o destino.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-114">The following sections first describe the general process of using the Recordset destination and then show a specific example of how to use the destination.</span></span>  
  
## <a name="general-steps-to-using-a-recordset-destination"></a><span data-ttu-id="8e3f9-115">Etapas gerais para o uso de um destino do conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="8e3f9-115">General Steps to Using a Recordset Destination</span></span>  
 <span data-ttu-id="8e3f9-116">O procedimento a seguir resume as etapas necessárias para salvar dados em um destino do Conjunto de Registros e usar o contêiner Loop Foreach para processar cada linha.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-116">The following procedure summarizes the steps that are required to save data to a Recordset destination, and then use the Foreach Loop container to process each row.</span></span>  
  
#### <a name="to-save-data-to-a-recordset-destination-and-process-each-row-by-using-the-foreach-loop-container"></a><span data-ttu-id="8e3f9-117">Para salvar dados em um destino do Conjunto de Registros e processar cada linha usando o contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="8e3f9-117">To save data to a Recordset destination and process each row by using the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="8e3f9-118">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], crie ou abra um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e3f9-118">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="8e3f9-119">Crie uma variável que conterá o conjunto de registros salvo na memória pelo destino do Conjunto de Registros e defina o tipo de variável como `Object`.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-119">Create a variable that will contain the recordset saved into memory by the Recordset destination, and set the variable's type to `Object`.</span></span>  
  
3.  <span data-ttu-id="8e3f9-120">Crie mais variáveis dos tipos apropriados para conter os valores de cada coluna no conjunto de registros que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-120">Create additional variables of the appropriate types to contain the values of each column in the recordset that you want to use.</span></span>  
  
4.  <span data-ttu-id="8e3f9-121">Adicione e configure o gerenciador de conexões necessário para a fonte de dados que você planeja usar no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-121">Add and configure the connection manager required by the data source that you plan to use in your data flow.</span></span>  
  
5.  <span data-ttu-id="8e3f9-122">Adicione uma tarefa de fluxo de dados ao pacote e, na guia Fluxo de Dados do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, configure fontes e transformações para carregar e transformar os dados.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-122">Add a Data Flow task to the package, and on the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, configure sources and transformations to load and transform the data.</span></span>  
  
6.  <span data-ttu-id="8e3f9-123">Adicione um destino do Conjunto de Registros ao fluxo de dados e conecte-o às transformações.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-123">Add a Recordset destination to the data flow and connect it to the transformations.</span></span> <span data-ttu-id="8e3f9-124">Para a propriedade `VariableName` do destino do Conjunto de Registros, insira o nome da variável criada para conter o conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-124">For the `VariableName` property of the Recordset destination, enter the name of the variable that you created to hold the recordset.</span></span>  
  
7.  <span data-ttu-id="8e3f9-125">Na guia Fluxo de Controle do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, adicione um contêiner Loop Foreach e conecte esse contêiner após a tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-125">On the Control Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container and connect this container after the Data Flow task.</span></span> <span data-ttu-id="8e3f9-126">Em seguida, abra o **Editor de Loop Foreach** para definir o contêiner com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-126">Then, open the **Foreach Loop Editor** to configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="8e3f9-127">Na página **Coleção** , selecione o Enumerador ADO Foreach.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-127">On the **Collection** page, select the Foreach ADO Enumerator.</span></span> <span data-ttu-id="8e3f9-128">Em seguida, para **Variável de origem do objeto ADO**, selecione a variável que contém o conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-128">Then, for **ADO object source variable**, select the variable that contains the recordset.</span></span>  
  
    2.  <span data-ttu-id="8e3f9-129">Na página **Mapeamentos de Variáveis** , mapeie o índice com base em zero de cada coluna que você deseja usar para a variável apropriada.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-129">On the **Variable Mappings** page, map the zero-based index of each column that you want to use to the appropriate variable.</span></span>  
  
         <span data-ttu-id="8e3f9-130">Em cada iteração do loop, o enumerador popula essas variáveis com os valores de coluna da linha atual.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-130">On each iteration of the loop, the enumerator populates these variables with the column values from the current row.</span></span>  
  
8.  <span data-ttu-id="8e3f9-131">Dentro do contêiner Loop Foreach, adicione e configure tarefas para processar uma linha do conjunto de registros de cada vez, lendo os valores das variáveis.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-131">Inside the Foreach Loop container, add and configure tasks to process one row of the recordset at a time by reading the values from the variables.</span></span>  
  
## <a name="example-of-using-the-recordset-destination"></a><span data-ttu-id="8e3f9-132">Exemplo de uso do destino do Conjunto de Registros</span><span class="sxs-lookup"><span data-stu-id="8e3f9-132">Example of Using the Recordset Destination</span></span>  
 <span data-ttu-id="8e3f9-133">No exemplo a seguir, a tarefa de fluxo de dados carrega informações sobre os funcionários de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] da tabela Sales.SalesPerson em um destino do Conjunto de Registros.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-133">In the following example, the Data Flow task loads information about [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] employees from the Sales.SalesPerson table into a Recordset destination.</span></span> <span data-ttu-id="8e3f9-134">Em seguida, um contêiner Loop Foreach lê uma linha de dados de cada vez e chama uma tarefa Enviar Email.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-134">Then, a Foreach Loop container reads one row of data at a time, and calls a Send Mail task.</span></span> <span data-ttu-id="8e3f9-135">A tarefa Enviar Email usa expressões para enviar uma mensagem de email personalizada a cada vendedor sobre o valor de seu bônus.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-135">The Send Mail task uses expressions to send a customized e-mail message to each salesperson about the amount of his or her bonus.</span></span>  
  
#### <a name="to-create-the-project-and-configure-the-variables"></a><span data-ttu-id="8e3f9-136">Para criar o projeto e configurar as variáveis</span><span class="sxs-lookup"><span data-stu-id="8e3f9-136">To create the project and configure the variables</span></span>  
  
1.  <span data-ttu-id="8e3f9-137">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], crie um novo projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e3f9-137">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="8e3f9-138">No menu **SSIS** , selecione **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-138">On the **SSIS** menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="8e3f9-139">Na janela **Variáveis** , crie as variáveis que conterão o conjunto de registros e os valores de coluna da linha atual:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-139">In the **Variables** window, create the variables that will hold the recordset and the column values from the current row:</span></span>  
  
    1.  <span data-ttu-id="8e3f9-140">Crie uma variável denominada `BonusRecordset` e defina seu tipo como `Object`.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-140">Create a variable named, `BonusRecordset`, and set its type to `Object`.</span></span>  
  
         <span data-ttu-id="8e3f9-141">A variável `BonusRecordset` contém o conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-141">The `BonusRecordset` variable holds the recordset.</span></span>  
  
    2.  <span data-ttu-id="8e3f9-142">Crie uma variável denominada `EmailAddress` e defina seu tipo como `String`.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-142">Create a variable named, `EmailAddress`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="8e3f9-143">A variável `EmailAddress` contém o endereço de email do vendedor.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-143">The `EmailAddress` variable holds the salesperson's e-mail address.</span></span>  
  
    3.  <span data-ttu-id="8e3f9-144">Crie uma variável denominada `FirstName` e defina seu tipo como `String`.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-144">Create a variable named, `FirstName`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="8e3f9-145">A variável `FirstName` contém o nome do vendedor.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-145">The `FirstName` variable holds the salesperson's first name.</span></span>  
  
    4.  <span data-ttu-id="8e3f9-146">Crie uma variável denominada `Bonus` e defina seu tipo como `Double`.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-146">Create a variable named, `Bonus`, and set its type to `Double`.</span></span>  
  
         <span data-ttu-id="8e3f9-147">A variável `Bonus` contém o valor do bônus do vendedor.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-147">The `Bonus` variable holds the amount of the salesperson's bonus.</span></span>  
  
#### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="8e3f9-148">Para configurar os gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="8e3f9-148">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="8e3f9-149">Na área Gerenciadores de Conexões do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, adicione e configure um novo gerenciador de conexões OLE DB que se conecta ao banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e3f9-149">In the Connection Managers area of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add and configure a new OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>  
  
     <span data-ttu-id="8e3f9-150">A fonte OLE DB na tarefa de fluxo de dados usará esse gerenciador de conexões para recuperar dados.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-150">The OLE DB source in the Data Flow task will use this connection manager to retrieve data.</span></span>  
  
2.  <span data-ttu-id="8e3f9-151">Na área Gerenciadores de Conexões, adicione e configure um novo gerenciador de conexões SMTP que se conecta ao servidor SMTP disponível.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-151">In the Connection Managers area, add and configure a new SMTP connection manager that connects to an available SMTP server.</span></span>  
  
     <span data-ttu-id="8e3f9-152">A tarefa Enviar Email dentro do contêiner Loop Foreach usará esse gerenciador de conexões para enviar emails.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-152">The Send Mail task inside the Foreach Loop container will use this connection manager to send emails.</span></span>  
  
#### <a name="to-configure-the-data-flow-and-the-recordset-destination"></a><span data-ttu-id="8e3f9-153">Para configurar o fluxo de dados e o destino do Conjunto de Registros</span><span class="sxs-lookup"><span data-stu-id="8e3f9-153">To configure the data flow and the Recordset Destination</span></span>  
  
1.  <span data-ttu-id="8e3f9-154">Na guia **Fluxo de Controle** do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, adicione uma tarefa de fluxo de dados à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-154">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Data Flow task to the design surface.</span></span>  
  
2.  <span data-ttu-id="8e3f9-155">Na guia **Fluxo de Dados** , adicione uma fonte OLE DB à tarefa de fluxo de dados e abra o **Editor de Origem OLE DB.**</span><span class="sxs-lookup"><span data-stu-id="8e3f9-155">On the **Data Flow** tab, add an OLE DB source to the Data Flow task, and then open the **OLE DB Source Editor.**</span></span>  
  
3.  <span data-ttu-id="8e3f9-156">Na página **Gerenciador de Conexões** do editor, defina a fonte com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-156">On the **Connection Manager** page of the editor, configure the source with the following settings:</span></span>  
  
    1.  <span data-ttu-id="8e3f9-157">Para **Gerenciador de Conexões OLE DB**, selecione o gerenciador de conexões OLE DB criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-157">For **OLE DB connection manager**, select the OLE DB connection manager that you previously created.</span></span>  
  
    2.  <span data-ttu-id="8e3f9-158">Para **Modo de acesso a dados**, selecione o **Comando SQL**.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-158">For **Data access mode**, select **SQL command**.</span></span>  
  
    3.  <span data-ttu-id="8e3f9-159">Em **Texto do comando SQL**, digite a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-159">For **SQL command text**, enter the following query:</span></span>  
  
        ```  
        SELECT     Person.Contact.EmailAddress, Person.Contact.FirstName, CONVERT(float, Sales.SalesPerson.Bonus) AS Bonus  
        FROM         Sales.SalesPerson INNER JOIN  
                              Person.Contact ON Sales.SalesPerson.SalesPersonID = Person.Contact.ContactID  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="8e3f9-160">É necessário converter o valor `currency` na coluna Bônus em um `float`, antes de carregar esse valor em uma variável de pacote cujo tipo é `Double`.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-160">You have to convert the `currency` value in the Bonus column to a `float` before you can load that value into a package variable whose type is `Double`.</span></span>  
  
4.  <span data-ttu-id="8e3f9-161">Na guia **Fluxo de Dados** , adicione um destino do Conjunto de Registros e conecte o destino após a fonte OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-161">On the **Data Flow** tab, add a Recordset destination, and connect the destination after the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="8e3f9-162">Abra o **Editor de Destino do Conjunto de Registros**e defina o destino com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-162">Open the **Recordset Destination Editor**, and configure the destination with the following settings:</span></span>  
  
    1.  <span data-ttu-id="8e3f9-163">Na guia **Propriedades do componente** , para `VariableName` propriedade, selecione `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="8e3f9-163">On the **Component Properties** tab, for `VariableName` property, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="8e3f9-164">Na guia **Colunas de Entrada** , selecione todas as três colunas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-164">On the **Input Columns** tab, select all three of the available columns.</span></span>  
  
#### <a name="to-configure-the-foreach-loop-container-and-run-the-package"></a><span data-ttu-id="8e3f9-165">Para configurar o contêiner Loop Foreach e executar o pacote</span><span class="sxs-lookup"><span data-stu-id="8e3f9-165">To configure the Foreach Loop container and run the package</span></span>  
  
1.  <span data-ttu-id="8e3f9-166">Na guia **Fluxo de Controle** do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, adicione um contêiner Loop Foreach e conecte esse contêiner após a tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-166">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container, and connect the container after the Data Flow task.</span></span>  
  
2.  <span data-ttu-id="8e3f9-167">Abra o **Editor de Loop Foreach**e defina o contêiner com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-167">Open the **Foreach Loop Editor**, and configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="8e3f9-168">Na página **coleção** , para o **enumerador**, selecione **enumerador ADO foreach**e, para **variável de origem de objeto ADO**, selecione `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="8e3f9-168">On the **Collection** page, for **Enumerator**, select **Foreach ADO Enumerator**, and for **ADO object source variable**, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="8e3f9-169">Na página **mapeamentos de variáveis** , mapeie `User::EmailAddress` para o índice 0, `User::FirstName` para o índice 1 e `User::Bonus` para o índice 2.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-169">On the **Variable Mappings** page, map `User::EmailAddress` to index 0, `User::FirstName` to index 1, and `User::Bonus` to index 2.</span></span>  
  
3.  <span data-ttu-id="8e3f9-170">Na guia **Fluxo de Controle** , dentro do contêiner Loop Foreach, adicione uma tarefa Enviar Email.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-170">On the **Control Flow** tab, inside the Foreach Loop container, add a Send Mail task.</span></span>  
  
4.  <span data-ttu-id="8e3f9-171">Abra o **Editor da Tarefa Enviar Email**e, na página **Email** , defina a tarefa com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-171">Open the **Send Mail Task Editor**, and then on the **Mail** page, configure the task with the following settings:</span></span>  
  
    1.  <span data-ttu-id="8e3f9-172">Para **SmtpConnection**, selecione o gerenciador de conexões SMTP configurado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-172">For **SmtpConnection**, select the SMTP connection manager that was configured previously.</span></span>  
  
    2.  <span data-ttu-id="8e3f9-173">Em **De**, insira um endereço de email apropriado.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-173">For **From**, enter an appropriate e-mail address.</span></span>  
  
         <span data-ttu-id="8e3f9-174">Se você usar seu próprio endereço de email, poderá confirmar a execução bem-sucedida do pacote.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-174">If you use your own e-mail address, you will be able to confirm that the package runs successfully.</span></span> <span data-ttu-id="8e3f9-175">Você receberá recibos de impossibilidade de entrega das mensagens enviadas pela tarefa Enviar Email aos vendedores fictícios de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e3f9-175">You will receive undeliverable receipts for the messages sent by the Send Mail task to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
    3.  <span data-ttu-id="8e3f9-176">Em **Para**, insira um endereço de email padrão.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-176">For **To**, enter a default e-mail address.</span></span>  
  
         <span data-ttu-id="8e3f9-177">Esse valor não será usado, mas será substituído em tempo de execução pelo endereço de email de cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-177">This value will not be used, but will be replaced at run time by the e-mail address of each salesperson.</span></span>  
  
    4.  <span data-ttu-id="8e3f9-178">Em **Assunto**, digite "Seu bônus anual".</span><span class="sxs-lookup"><span data-stu-id="8e3f9-178">For **Subject**, enter "Your annual bonus".</span></span>  
  
    5.  <span data-ttu-id="8e3f9-179">Em **MessageSourceType**, selecione **Entrada Direta**.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-179">For **MessageSourceType**, select **Direct Input**.</span></span>  
  
5.  <span data-ttu-id="8e3f9-180">Na página **Expressões** do **Editor da Tarefa Enviar Email**, clique no botão de reticências ( **...** ) para abrir o **Editor de Expressões de Propriedade**.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-180">On the **Expressions** page of the **Send Mail Task Editor**, click the ellipsis button (**...**) to open the **Property Expressions Editor**.</span></span>  
  
6.  <span data-ttu-id="8e3f9-181">No **Editor de Expressões de Propriedade**, insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-181">In the **Property Expressions Editor**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="8e3f9-182">Em **ToLine**, adicione a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-182">For **ToLine**, add the following expression:</span></span>  
  
        ```  
        @[User::EmailAddress]  
        ```  
  
    2.  <span data-ttu-id="8e3f9-183">Para a propriedade **MessageSource** , adicione a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="8e3f9-183">For the **MessageSource** property, add the following expression:</span></span>  
  
        ```  
        "Dear " +  @[User::FirstName] + ": The amount of your bonus for this year is $" +  (DT_WSTR, 12) @[User::Bonus] + ". Thank you!"  
        ```  
  
7.  <span data-ttu-id="8e3f9-184">Execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="8e3f9-184">Run the package.</span></span>  
  
     <span data-ttu-id="8e3f9-185">Caso tenha especificado um servidor SMTP válido e fornecido seu próprio endereço de email, você receberá recibos de impossibilidade de entrega que a tarefa Enviar Email envia aos vendedores fictícios de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e3f9-185">If you have specified a valid SMTP server and provided your own e-mail address, you will receive undeliverable receipts for the messages that the Send Mail task sends to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
  
