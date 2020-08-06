---
title: Carregando a saída de um pacote local | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow [Integration Services], loading results
- loading data flow results
ms.assetid: aba8ecb7-0dcf-40d0-a2a8-64da0da94b93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6799e593ab9d5ae1a9358bf54f4927838991ebd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684801"
---
# <a name="loading-the-output-of-a-local-package"></a><span data-ttu-id="4e33f-102">Carregando a saída de um pacote local</span><span class="sxs-lookup"><span data-stu-id="4e33f-102">Loading the Output of a Local Package</span></span>
  <span data-ttu-id="4e33f-103">Aplicativos cliente podem ler a saída de pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] quando a saída é salva em destinos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio de [!INCLUDE[vstecado](../../includes/vstecado-md.md)] ou quando a saída é salva em um destino de arquivo simples por meio das classes no namespace **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="4e33f-103">Client applications can read the output of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages when the output is saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destinations by using [!INCLUDE[vstecado](../../includes/vstecado-md.md)], or when the output is saved to a flat file destination by using the classes in the **System.IO** namespace.</span></span> <span data-ttu-id="4e33f-104">Entretanto, um aplicativo cliente também consegue ler a saída de um pacote diretamente da memória, sem precisar de uma etapa intermediária para manter os dados.</span><span class="sxs-lookup"><span data-stu-id="4e33f-104">However, a client application can also read the output of a package directly from memory, without the need for an intermediate step to persist the data.</span></span> <span data-ttu-id="4e33f-105">A chave para essa solução é o `Microsoft.SqlServer.Dts.DtsClient` namespace, que contém implementações especializadas `IDbConnection` das `IDbCommand` interfaces, e **IDbDataParameter** do namespace **System. Data** .</span><span class="sxs-lookup"><span data-stu-id="4e33f-105">The key to this solution is the `Microsoft.SqlServer.Dts.DtsClient` namespace, which contains specialized implementations of the `IDbConnection`, `IDbCommand`, and **IDbDataParameter** interfaces from the **System.Data** namespace.</span></span> <span data-ttu-id="4e33f-106">O assembly Microsoft.SqlServer.Dts.DtsClient.dll é instalado por padrão em **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="4e33f-106">The assembly Microsoft.SqlServer.Dts.DtsClient.dll is installed by default in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

> [!NOTE]
>  <span data-ttu-id="4e33f-107">O procedimento descrito neste tópico exige que a propriedade DelayValidation da tarefa Fluxo de Dados e de qualquer objeto pai seja definida com seu valor padrão **False**.</span><span class="sxs-lookup"><span data-stu-id="4e33f-107">The procedure described in this topic requires that the DelayValidation property of the Data Flow task and of any parent objects be set to its default value of **False**.</span></span>

## <a name="description"></a><span data-ttu-id="4e33f-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="4e33f-108">Description</span></span>
 <span data-ttu-id="4e33f-109">Esse procedimento demonstra como desenvolver um aplicativo cliente em código gerenciado que carrega a saída de um pacote com um destino do DataReader diretamente da memória.</span><span class="sxs-lookup"><span data-stu-id="4e33f-109">This procedure demonstrates how to develop a client application in managed code that loads the output of a package with a DataReader destination directly from memory.</span></span> <span data-ttu-id="4e33f-110">As etapas resumidas aqui são demonstradas no código de exemplo que segue.</span><span class="sxs-lookup"><span data-stu-id="4e33f-110">The steps summarized here are demonstrated in the code sample that follows.</span></span>

#### <a name="to-load-data-package-output-into-a-client-application"></a><span data-ttu-id="4e33f-111">Para carregar a saída de pacote de dados em um aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="4e33f-111">To load data package output into a client application</span></span>

1.  <span data-ttu-id="4e33f-112">No pacote, configure um destino do DataReader para receber a saída que você quer ler no aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="4e33f-112">In the package, configure a DataReader destination to receive the output that you want to read into the client application.</span></span> <span data-ttu-id="4e33f-113">Dê ao destino do DataReader um nome descritivo, pois você usará esse nome em seu aplicativo cliente posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4e33f-113">Give the DataReader destination a descriptive name, since you will use this name later in your client application.</span></span> <span data-ttu-id="4e33f-114">Anote o nome do destino do DataReader.</span><span class="sxs-lookup"><span data-stu-id="4e33f-114">Make a note of the name of the DataReader destination.</span></span>

2.  <span data-ttu-id="4e33f-115">No projeto de desenvolvimento, defina uma referência ao `Microsoft.SqlServer.Dts.DtsClient` namespace localizando o assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span><span class="sxs-lookup"><span data-stu-id="4e33f-115">In the development project, set a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by locating the assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span></span> <span data-ttu-id="4e33f-116">Por padrão, esse assembly é instalado em **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="4e33f-116">By default, this assembly is installed in **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span></span> <span data-ttu-id="4e33f-117">Importe o namespace para seu código usando o C# `Using` ou a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` instrução.</span><span class="sxs-lookup"><span data-stu-id="4e33f-117">Import the namespace into your code by using the C# `Using` or the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` statement.</span></span>

3.  <span data-ttu-id="4e33f-118">Em seu código, crie um objeto do tipo `DtsClient.DtsConnection` com uma cadeia de conexão que contenha os parâmetros de linha de comando exigidos pelo **dtexec.exe** para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="4e33f-118">In your code, create an object of type `DtsClient.DtsConnection` with a connection string that contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="4e33f-119">Para saber mais, veja [dtexec Utility](../packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4e33f-119">For more information, see [dtexec Utility](../packages/dtexec-utility.md).</span></span> <span data-ttu-id="4e33f-120">Em seguida, abra a conexão com essa cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="4e33f-120">Then open the connection with this connection string.</span></span> <span data-ttu-id="4e33f-121">Também use o utilitário **dtexecui** para criar a cadeia de conexão necessária visualmente.</span><span class="sxs-lookup"><span data-stu-id="4e33f-121">You can also use the **dtexecui** utility to create the required connection string visually.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4e33f-122">O código de exemplo demonstra o carregamento do pacote do sistema de arquivos usando a sintaxe `/FILE <path and filename>`.</span><span class="sxs-lookup"><span data-stu-id="4e33f-122">The sample code demonstrates loading the package from the file system by using the `/FILE <path and filename>` syntax.</span></span> <span data-ttu-id="4e33f-123">Contudo, você também pode carregar o pacote do banco de dados MSDB usando a sintaxe `/SQL <package name>` ou do repositório de pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usando a sintaxe `/DTS \<folder name>\<package name>`.</span><span class="sxs-lookup"><span data-stu-id="4e33f-123">However you can also load the package from the MSDB database by using the `/SQL <package name>` syntax, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by using the `/DTS \<folder name>\<package name>` syntax.</span></span>

4.  <span data-ttu-id="4e33f-124">Crie um objeto do tipo `DtsClient.DtsCommand` que use o `DtsConnection` criado anteriormente e defina sua propriedade `CommandText` com o nome de destino do DataReader no pacote.</span><span class="sxs-lookup"><span data-stu-id="4e33f-124">Create an object of type `DtsClient.DtsCommand` that uses the previously created `DtsConnection` and set its `CommandText` property to the name of the DataReader destination in the package.</span></span> <span data-ttu-id="4e33f-125">Em seguida, chame o método `ExecuteReader` do objeto de comando para carregar os resultados do pacote em um DataReader novo.</span><span class="sxs-lookup"><span data-stu-id="4e33f-125">Then call the `ExecuteReader` method of the command object to load the package results into a new DataReader.</span></span>

5.  <span data-ttu-id="4e33f-126">Uma alternativa é parametrizar indiretamente a saída do pacote usando a coleção de objetos `DtsDataParameter` no objeto `DtsCommand` para passar valores para variáveis definidas no pacote.</span><span class="sxs-lookup"><span data-stu-id="4e33f-126">Optionally, you can indirectly parameterize the output of the package by using the collection of `DtsDataParameter` objects on the `DtsCommand` object to pass values to variables defined in the package.</span></span> <span data-ttu-id="4e33f-127">No pacote, você pode usar essas variáveis como parâmetros de consulta ou em expressões para afetar os resultados retornados para o destino do DataReader.</span><span class="sxs-lookup"><span data-stu-id="4e33f-127">Within the package, you can use these variables as query parameters or in expressions to affect the results returned to the DataReader destination.</span></span> <span data-ttu-id="4e33f-128">Você deve definir essas variáveis no pacote no namespace **DtsClient** antes de poder usá-las com o `DtsDataParameter` objeto de um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="4e33f-128">You must define these variables in the package in the **DtsClient** namespace before you can use them with the `DtsDataParameter` object from a client application.</span></span> <span data-ttu-id="4e33f-129">(Talvez seja necessário clicar no botão da barra de ferramentas **escolher colunas variáveis** na janela **variáveis** para exibir a coluna **namespace** .) No código do cliente, quando você adiciona um `DtsDataParameter` à `Parameters` coleção de `DtsCommand` , omita a referência de namespace DtsClient do nome da variável.</span><span class="sxs-lookup"><span data-stu-id="4e33f-129">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.) In your client code, when you add a `DtsDataParameter` to the `Parameters` collection of the `DtsCommand`, omit the DtsClient namespace reference from the variable name.</span></span> <span data-ttu-id="4e33f-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4e33f-130">For example:</span></span>

    ```
    command.Parameters.Add(new DtsDataParameter("MyVariable", 1));
    ```

6.  <span data-ttu-id="4e33f-131">Chame repetidamente o método `Read` do DataReader, conforme necessário, para executar o loop pelas linhas de dados de saída.</span><span class="sxs-lookup"><span data-stu-id="4e33f-131">Call the `Read` method of the DataReader repeatedly as needed to loop through the rows of output data.</span></span> <span data-ttu-id="4e33f-132">Use os dados ou salve-os para serem usados posteriormente no aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="4e33f-132">Use the data, or save the data for later use, in the client application.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="4e33f-133">O método `Read` dessa implementação do DataReader retorna `true` uma vez mais depois que a última linha de dados é lida.</span><span class="sxs-lookup"><span data-stu-id="4e33f-133">The `Read` method of this implementation of the DataReader returns `true` one more time after the last row of data has been read.</span></span> <span data-ttu-id="4e33f-134">Isso dificulta o uso do código usual que executa o loop no DataReader enquanto `Read` retorna `true`.</span><span class="sxs-lookup"><span data-stu-id="4e33f-134">This makes it difficult to use the usual code that loops through the DataReader while `Read` returns `true`.</span></span> <span data-ttu-id="4e33f-135">Se seu código tentar fechar o DataReader ou a conexão depois de ler o número de linhas esperado, sem uma chamada adicional final para o método `Read`, o código gerará uma exceção sem-tratamento.</span><span class="sxs-lookup"><span data-stu-id="4e33f-135">If your code attempts to close the DataReader or the connection after reading the expected number of rows, without an additional, final call to the `Read` method, the code will raise an unhandled exception.</span></span> <span data-ttu-id="4e33f-136">Entretanto, se seu código tentar ler dados nessa iteração final através de um loop, quando `Read` ainda retorna `true`, mas a última linha tiver passado, o código gerará uma `ApplicationException` sem-tratamento com a mensagem "O IDataReader SSIS passou do final do conjunto de resultados".</span><span class="sxs-lookup"><span data-stu-id="4e33f-136">However, if your code attempts to read data on this final iteration through a loop, when `Read` still returns `true` but the last row has been passed, the code will raise an unhandled `ApplicationException` with the message, "The SSIS IDataReader is past the end of the resultset."</span></span> <span data-ttu-id="4e33f-137">Esse comportamento é diferente de outras implementações do DataReader.</span><span class="sxs-lookup"><span data-stu-id="4e33f-137">This behavior is different from that of other DataReader implementations.</span></span> <span data-ttu-id="4e33f-138">Entretanto, ao usar um loop para ler as linhas no DataReader enquanto `Read` retorna `true`, você precisa gravar o código para pegar, testar e descartar essa `ApplicationException` antecipada na última chamada bem sucedida do método `Read`.</span><span class="sxs-lookup"><span data-stu-id="4e33f-138">Therefore, when using a loop to read through the rows in the DataReader while `Read` returns `true`, you need to write code to catch, test, and discard this anticipated `ApplicationException` on the last successful call to the `Read` method.</span></span> <span data-ttu-id="4e33f-139">Ou, se você souber antes o número de linhas esperado, você poderá processar as linhas e depois chamar o método `Read` mais uma vez antes de fechar o DataReader e a conexão.</span><span class="sxs-lookup"><span data-stu-id="4e33f-139">Or, if you know in advance the number of rows expected, you can process the rows, and then call the `Read` method one more time before closing the DataReader and the connection.</span></span>

7.  <span data-ttu-id="4e33f-140">Chame o método `Dispose` do objeto `DtsCommand`.</span><span class="sxs-lookup"><span data-stu-id="4e33f-140">Call the `Dispose` method of the `DtsCommand` object.</span></span> <span data-ttu-id="4e33f-141">Isso é particularmente importante se você usou qualquer objeto `DtsDataParameter`.</span><span class="sxs-lookup"><span data-stu-id="4e33f-141">This is particularly important if you have used any `DtsDataParameter` objects.</span></span>

8.  <span data-ttu-id="4e33f-142">Feche o DataReader e os objetos de conexão.</span><span class="sxs-lookup"><span data-stu-id="4e33f-142">Close the DataReader and the connection objects.</span></span>

## <a name="example"></a><span data-ttu-id="4e33f-143">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4e33f-143">Example</span></span>
 <span data-ttu-id="4e33f-144">O exemplo a seguir executa um pacote que calcula um único valor de agregação, salva esse valor em um destino do DataReader e o lê do DataReader e o exibe em uma caixa de texto em um formulário do Windows.</span><span class="sxs-lookup"><span data-stu-id="4e33f-144">The following example runs a package that calculates a single aggregate value and saves the value to a DataReader destination, and then reads this value from the DataReader and displays the value in a text box on a Windows Form.</span></span>

 <span data-ttu-id="4e33f-145">O uso de parâmetros não é necessário ao carregar a saída de um pacote em um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="4e33f-145">The use of parameters is not required when loading the output of a package into a client application.</span></span> <span data-ttu-id="4e33f-146">Se você não quiser usar um parâmetro, poderá omitir o uso da variável no namespace **DtsClient** e omitir o código que usa o `DtsDataParameter` objeto.</span><span class="sxs-lookup"><span data-stu-id="4e33f-146">If you do not want to use a parameter, you can omit the use of the variable in the **DtsClient** namespace, and omit the code that uses the `DtsDataParameter` object.</span></span>

#### <a name="to-create-the-test-package"></a><span data-ttu-id="4e33f-147">Para criar o pacote de teste</span><span class="sxs-lookup"><span data-stu-id="4e33f-147">To create the test package</span></span>

1.  <span data-ttu-id="4e33f-148">Crie um novo pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e33f-148">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="4e33f-149">O código de exemplo usa "DtsClientWParamPkg.dtsx" como o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="4e33f-149">The sample code uses "DtsClientWParamPkg.dtsx" as the name of the package.</span></span>

2.  <span data-ttu-id="4e33f-150">Adicione uma variável do tipo Cadeia de caracteres ao namespace DtsClient.</span><span class="sxs-lookup"><span data-stu-id="4e33f-150">Add a variable of type String in the DtsClient namespace.</span></span> <span data-ttu-id="4e33f-151">O código de exemplo usa País como nome da variável.</span><span class="sxs-lookup"><span data-stu-id="4e33f-151">The sample code use Country as the name of the variable.</span></span> <span data-ttu-id="4e33f-152">(Talvez você precise clicar no botão de barra de ferramentas **Escolher Colunas de Variáveis** na janela **Variáveis** para exibir a coluna **Namespace**.)</span><span class="sxs-lookup"><span data-stu-id="4e33f-152">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.)</span></span>

3.  <span data-ttu-id="4e33f-153">Adicione um gerenciador de conexões do OLE DB que se conecta ao banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e33f-153">Add an OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>

4.  <span data-ttu-id="4e33f-154">Acrescente uma tarefa de fluxo de dados ao pacote e alterne para a superfície de design de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="4e33f-154">Add a data flow task to the package and switch to the Data Flow design surface.</span></span>

5.  <span data-ttu-id="4e33f-155">Adicione uma origem de OLE DB ao fluxo de dados e configure-a para usar o gerenciador de conexões OLE DB criado anteriormente, e o seguinte comando SQL:</span><span class="sxs-lookup"><span data-stu-id="4e33f-155">Add an OLE DB source to the data flow and configure it to use the OLE DB connection manager created previously, and the following SQL command:</span></span>

    ```
    SELECT * FROM Sales.vIndividualCustomer WHERE CountryRegionName = ?
    ```

6.  <span data-ttu-id="4e33f-156">Clique em `Parameters` e, na caixa de diálogo **definir parâmetros de consulta** , mapeie o parâmetro de entrada único na consulta, Parameter0, para a variável DtsClient:: Country.</span><span class="sxs-lookup"><span data-stu-id="4e33f-156">Click `Parameters` and, in the **Set Query Parameters** dialog box, map the single input parameter in the query, Parameter0, to the DtsClient::Country variable.</span></span>

7.  <span data-ttu-id="4e33f-157">Acrescente uma transformação Agregação ao fluxo de dados e conecte a saída da origem de OLE DB à transformação.</span><span class="sxs-lookup"><span data-stu-id="4e33f-157">Add an Aggregate transformation to the data flow, and connect the output of the OLE DB source to the transformation.</span></span> <span data-ttu-id="4e33f-158">Abra o editor de transformação agregação e configure-o para executar uma operação "contagem total" em todas as colunas de entrada (\*) e para gerar o valor agregado com o alias CustomerCount.</span><span class="sxs-lookup"><span data-stu-id="4e33f-158">Open the Aggregate Transformation Editor and configure it to perform a "Count all" operation on all input columns (\*) and to output the aggregated value with the alias CustomerCount.</span></span>

8.  <span data-ttu-id="4e33f-159">Acrescente um destino de DataReader ao fluxo de dados e conecte a saída da transformação Agregação a esse destino.</span><span class="sxs-lookup"><span data-stu-id="4e33f-159">Add a DataReader destination to the data flow and connect the output of the Aggregate transformation to the DataReader destination.</span></span> <span data-ttu-id="4e33f-160">O código de exemplo usa "DataReaderDest" como o nome do DataReader.</span><span class="sxs-lookup"><span data-stu-id="4e33f-160">The sample code uses "DataReaderDest" as the name of the DataReader.</span></span> <span data-ttu-id="4e33f-161">Selecione a única coluna de entrada disponível, CustomerCount, para o destino.</span><span class="sxs-lookup"><span data-stu-id="4e33f-161">Select the single available input column, CustomerCount, for the destination.</span></span>

9. <span data-ttu-id="4e33f-162">Salve o pacote.</span><span class="sxs-lookup"><span data-stu-id="4e33f-162">Save the package.</span></span> <span data-ttu-id="4e33f-163">O aplicativo de teste criado em seguida executará o pacote e recuperará sua saída diretamente da memória.</span><span class="sxs-lookup"><span data-stu-id="4e33f-163">The test application created next will run the package and retrieve its output directly from memory.</span></span>

#### <a name="to-create-the-test-application"></a><span data-ttu-id="4e33f-164">Para criar o aplicativo de teste</span><span class="sxs-lookup"><span data-stu-id="4e33f-164">To create the test application</span></span>

1.  <span data-ttu-id="4e33f-165">Crie um novo aplicativo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4e33f-165">Create a new Windows Forms application.</span></span>

2.  <span data-ttu-id="4e33f-166">Adicione uma referência ao `Microsoft.SqlServer.Dts.DtsClient` namespace navegando até o assembly do mesmo nome em **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="4e33f-166">Add a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by browsing to the assembly of the same name in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

3.  <span data-ttu-id="4e33f-167">Copie e cole o código de exemplo seguinte no módulo de código para o formulário.</span><span class="sxs-lookup"><span data-stu-id="4e33f-167">Copy and paste the following sample code into the code module for the form.</span></span>

4.  <span data-ttu-id="4e33f-168">Modifique o valor da `dtexecArgs` variável conforme necessário para que ela contenha os parâmetros de linha de comando exigidos pelo **dtexec.exe** para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="4e33f-168">Modify the value of the `dtexecArgs` variable as required so that it contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="4e33f-169">O código de exemplo carrega o pacote do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4e33f-169">The sample code loads the package from the file system.</span></span>

5.  <span data-ttu-id="4e33f-170">Modifique o valor da `dataReaderName` variável conforme necessário para que ela contenha o nome do destino DataReader no pacote.</span><span class="sxs-lookup"><span data-stu-id="4e33f-170">Modify the value of the `dataReaderName` variable as required so that it contains the name of the DataReader destination in the package.</span></span>

6.  <span data-ttu-id="4e33f-171">Coloque um botão e uma caixa de texto no formulário.</span><span class="sxs-lookup"><span data-stu-id="4e33f-171">Put a button and a text box on the form.</span></span> <span data-ttu-id="4e33f-172">O código de exemplo usa `btnRun` como o nome do botão e `txtResults` como o nome da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="4e33f-172">The sample code uses `btnRun` as the name of the button, and `txtResults` as the name of the text box.</span></span>

7.  <span data-ttu-id="4e33f-173">Execute o aplicativo e clique no botão.</span><span class="sxs-lookup"><span data-stu-id="4e33f-173">Run the application and click the button.</span></span> <span data-ttu-id="4e33f-174">Após uma pequena pausa, enquanto o pacote é executado, você deverá ver o valor de agregação calculado pelo pacote (a contagem de clientes no Canadá) exibido na caixa de texto do formulário.</span><span class="sxs-lookup"><span data-stu-id="4e33f-174">After a brief pause while the package runs, you should see the aggregate value calculated by the package (the count of customers in Canada) displayed in the text box on the form.</span></span>

### <a name="sample-code"></a><span data-ttu-id="4e33f-175">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="4e33f-175">Sample Code</span></span>

```vb
Imports System.Data
Imports Microsoft.SqlServer.Dts.DtsClient

Public Class Form1

  Private Sub btnRun_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnRun.Click

    Dim dtexecArgs As String
    Dim dataReaderName As String
    Dim countryName As String

    Dim dtsConnection As DtsConnection
    Dim dtsCommand As DtsCommand
    Dim dtsDataReader As IDataReader
    Dim dtsParameter As DtsDataParameter

    Windows.Forms.Cursor.Current = Cursors.WaitCursor

    dtexecArgs = "/FILE ""C:\...\DtsClientWParamPkg.dtsx"""
    dataReaderName = "DataReaderDest"
    countryName = "Canada"

    dtsConnection = New DtsConnection()
    With dtsConnection
      .ConnectionString = dtexecArgs
      .Open()
    End With

    dtsCommand = New DtsCommand(dtsConnection)
    dtsCommand.CommandText = dataReaderName

    dtsParameter = New DtsDataParameter("Country", DbType.String)
    dtsParameter.Direction = ParameterDirection.Input
    dtsCommand.Parameters.Add(dtsParameter)

    dtsParameter.Value = countryName

    dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default)

    With dtsDataReader
      .Read()
      txtResults.Text = .GetInt32(0).ToString("N0")
    End With

    'After reaching the end of data rows,
    ' call the Read method one more time.
    Try
      dtsDataReader.Read()
    Catch ex As Exception
      MessageBox.Show("Exception on final call to Read method:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception on final call to Read method", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    ' The following method is a best practice, and is
    '  required when using DtsDataParameter objects.
    dtsCommand.Dispose()

    Try
      dtsDataReader.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing DataReader:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing DataReader", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Try
      dtsConnection.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing connection:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing connection", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Windows.Forms.Cursor.Current = Cursors.Default

  End Sub

End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Data;
using Microsoft.SqlServer.Dts.DtsClient;

namespace DtsClientWParamCS
{
  public partial class Form1 : Form
  {
    public Form1()
    {
      InitializeComponent();
      this.btnRun.Click += new System.EventHandler(this.btnRun_Click);
    }

    private void btnRun_Click(object sender, EventArgs e)
    {
      string dtexecArgs;
      string dataReaderName;
      string countryName;

      DtsConnection dtsConnection;
      DtsCommand dtsCommand;
      IDataReader dtsDataReader;
      DtsDataParameter dtsParameter;

      Cursor.Current = Cursors.WaitCursor;

      dtexecArgs = @"/FILE ""C:\...\DtsClientWParamPkg.dtsx""";
      dataReaderName = "DataReaderDest";
      countryName = "Canada";

      dtsConnection = new DtsConnection();
      {
        dtsConnection.ConnectionString = dtexecArgs;
        dtsConnection.Open();
      }

      dtsCommand = new DtsCommand(dtsConnection);
      dtsCommand.CommandText = dataReaderName;

      dtsParameter = new DtsDataParameter("Country", DbType.String);
      dtsParameter.Direction = ParameterDirection.Input;
      dtsCommand.Parameters.Add(dtsParameter);

      dtsParameter.Value = countryName;

      dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default);

      {
        dtsDataReader.Read();
        txtResults.Text = dtsDataReader.GetInt32(0).ToString("N0");
      }

      //After reaching the end of data rows,
      // call the Read method one more time.
      try
      {
        dtsDataReader.Read();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception on final call to Read method:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception on final call to Read method", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      // The following method is a best practice, and is
      //  required when using DtsDataParameter objects.
      dtsCommand.Dispose();

      try
      {
        dtsDataReader.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing DataReader:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing DataReader", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      try
      {
        dtsConnection.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing connection:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing connection", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      Cursor.Current = Cursors.Default;

    }
  }
}
```

<span data-ttu-id="4e33f-176">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4e33f-176">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4e33f-177">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="4e33f-177">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4e33f-178">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="4e33f-178">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4e33f-179">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="4e33f-179">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e33f-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e33f-180">See Also</span></span>
 <span data-ttu-id="4e33f-181">[Noções básicas sobre as diferenças entre o carregamento de execução local e remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [e a execução de um pacote local](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [carregando e executando um pacote remoto programaticamente](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span><span class="sxs-lookup"><span data-stu-id="4e33f-181">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span></span>


