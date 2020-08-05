---
title: Compreender o Component Object Model do Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], object model
ms.assetid: 2a0aae82-39cc-4423-b09a-72d2f61033bd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a11556b00efc5749e8ddb895712d6c61f2459d8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573195"
---
# <a name="understanding-the-script-component-object-model"></a><span data-ttu-id="e2b01-102">Compreendendo o Component Object Model Script</span><span class="sxs-lookup"><span data-stu-id="e2b01-102">Understanding the Script Component Object Model</span></span>
  <span data-ttu-id="e2b01-103">Conforme discutido em [codificando e Depurando o componente Script] (.. /Extending-Packages-scripting/data-Flow-script-Component/Coding-and-Debugging-The-script-Component.MD, o projeto de componente de script contém três itens de projeto:</span><span class="sxs-lookup"><span data-stu-id="e2b01-103">As discussed in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md, the Script component project contains three project items:</span></span>

1.  <span data-ttu-id="e2b01-104">O item `ScriptMain`, que contém a classe `ScriptMain` na qual você escreve seu código.</span><span class="sxs-lookup"><span data-stu-id="e2b01-104">The `ScriptMain` item, which contains the `ScriptMain` class in which you write your code.</span></span> <span data-ttu-id="e2b01-105">A classe `ScriptMain` herda da classe `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-105">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

2.  <span data-ttu-id="e2b01-106">O item `ComponentWrapper`, que contém a classe `UserComponent`, uma instância do <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> que contém os métodos e propriedades que você utilizará para processar dados e interagir com o pacote.</span><span class="sxs-lookup"><span data-stu-id="e2b01-106">The `ComponentWrapper` item, which contains the `UserComponent` class, an instance of <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> that contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="e2b01-107">O item `ComponentWrapper` também contém as classes de coleção `Connections` e `Variables`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-107">The `ComponentWrapper` item also contains `Connections` and `Variables` collection classes.</span></span>

3.  <span data-ttu-id="e2b01-108">O item `BufferWrapper`, que contém classes herdadas de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> para cada entrada e saída, e propriedades digitadas para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="e2b01-108">The `BufferWrapper` item, which contains classes that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output, and typed properties for each column.</span></span>

 <span data-ttu-id="e2b01-109">À medida que você escrever seu código no item `ScriptMain`, usará os objetos, métodos e propriedades discutidos nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="e2b01-109">As you write your code in the `ScriptMain` item, you will use the objects, methods, and properties discussed in this topic.</span></span> <span data-ttu-id="e2b01-110">Cada componente não usará todos os métodos listados aqui; porém, quando usados, eles obedecerão à sequência mostrada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-110">Each component will not use all the methods listed here; however, when used, they are used in the sequence shown.</span></span>

 <span data-ttu-id="e2b01-111">A classe base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> não contém códigos de implementação para os métodos discutidos nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="e2b01-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class does not contain any implementation code for the methods discussed in this topic.</span></span> <span data-ttu-id="e2b01-112">Portanto, é desnecessário, mas inofensivo, adicionar uma chamada à implementação de classe base na sua própria implementação do método.</span><span class="sxs-lookup"><span data-stu-id="e2b01-112">Therefore it is unnecessary, but harmless, to add a call to the base class implementation to your own implementation of the method.</span></span>

 <span data-ttu-id="e2b01-113">Para obter informações sobre como usar os métodos e propriedades dessas classes em um tipo específico de componente Script, consulte a seção [Exemplos adicionais de componente de script](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e2b01-113">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="e2b01-114">Os tópicos de exemplo também contêm exemplos de código completos.</span><span class="sxs-lookup"><span data-stu-id="e2b01-114">The example topics also contain complete code samples.</span></span>

## <a name="acquireconnections-method"></a><span data-ttu-id="e2b01-115">Método AcquireConnections</span><span class="sxs-lookup"><span data-stu-id="e2b01-115">AcquireConnections Method</span></span>
 <span data-ttu-id="e2b01-116">Origens e destinos geralmente precisam se conectar a uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="e2b01-116">Sources and destinations generally must connect to an external data source.</span></span> <span data-ttu-id="e2b01-117">Substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> para recuperar a conexão ou as informações de conexão do gerenciador de conexões apropriado.</span><span class="sxs-lookup"><span data-stu-id="e2b01-117">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to retrieve the connection or the connection information from the appropriate connection manager.</span></span>

 <span data-ttu-id="e2b01-118">O exemplo a seguir retorna um `System.Data.SqlClient.SqlConnection` de um gerenciador de conexões ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e2b01-118">The following example returns a `System.Data.SqlClient.SqlConnection` from an ADO.NET connection manager.</span></span>

```vb
Dim connMgr As IDTSConnectionManager100
Dim sqlConn As SqlConnection

Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    connMgr = Me.Connections.MyADONETConnection
    sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

End Sub
```

 <span data-ttu-id="e2b01-119">O exemplo a seguir retorna um caminho completo e o nome de arquivo de um Gerenciador de Conexões de Arquivos Simples e, em seguida, abre o arquivo por meio de um `System.IO.StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-119">The following example returns a complete path and file name from a Flat File Connection Manager, and then opens the file by using a `System.IO.StreamReader`.</span></span>

```vb
Private textReader As StreamReader
Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    Dim connMgr As IDTSConnectionManager100 = _
        Me.Connections.MyFlatFileSrcConnectionManager
    Dim exportedAddressFile As String = _
        CType(connMgr.AcquireConnection(Nothing), String)
    textReader = New StreamReader(exportedAddressFile)

End Sub
```

## <a name="preexecute-method"></a><span data-ttu-id="e2b01-120">Método PreExecute</span><span class="sxs-lookup"><span data-stu-id="e2b01-120">PreExecute Method</span></span>
 <span data-ttu-id="e2b01-121">Substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> sempre que existir um processamento que precisa ser executado apenas uma vez antes de iniciar o processamento de linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-121">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only before you start processing rows of data.</span></span> <span data-ttu-id="e2b01-122">Por exemplo, em um destino, talvez você queira configurar o comando com parâmetros que o destino utilizará para inserir cada linha de dados na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-122">For example, in a destination, you may want to configure the parameterized command that the destination will use to insert each row of data into the data source.</span></span>

```vb
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter
...
    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub
```

```csharp
SqlConnection sqlConn; 
SqlCommand sqlCmd; 
SqlParameter sqlParam; 

public override void PreExecute() 
{ 

    sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " + "VALUES(@addressid, @city)", sqlConn); 
    sqlParam = new SqlParameter("@addressid", SqlDbType.Int); 
    sqlCmd.Parameters.Add(sqlParam); 
    sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30); 
    sqlCmd.Parameters.Add(sqlParam); 

}
```

## <a name="processing-inputs-and-outputs"></a><span data-ttu-id="e2b01-123">Processando entradas e saídas</span><span class="sxs-lookup"><span data-stu-id="e2b01-123">Processing Inputs and Outputs</span></span>

### <a name="processing-inputs"></a><span data-ttu-id="e2b01-124">Processando entradas</span><span class="sxs-lookup"><span data-stu-id="e2b01-124">Processing Inputs</span></span>
 <span data-ttu-id="e2b01-125">Componentes Script que são configurados como transformações ou destinos têm uma entrada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-125">Script components that are configured as transformations or destinations have one input.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="e2b01-126">O que o item de projeto BufferWrapper fornece</span><span class="sxs-lookup"><span data-stu-id="e2b01-126">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="e2b01-127">Para cada entrada configurada, o item de projeto `BufferWrapper` contém uma classe que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> e tem o mesmo nome que a entrada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-127">For each input that you have configured, the `BufferWrapper` project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the input.</span></span> <span data-ttu-id="e2b01-128">Cada classe de buffer de entrada contém as seguintes propriedades, funções e métodos:</span><span class="sxs-lookup"><span data-stu-id="e2b01-128">Each input buffer class contains the following properties, functions, and methods:</span></span>

-   <span data-ttu-id="e2b01-129">Propriedades de acessador nomeadas, digitadas para cada coluna de entrada selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-129">Named, typed accessor properties for each selected input column.</span></span> <span data-ttu-id="e2b01-130">Essas propriedades são somente leitura ou de leitura/gravação, dependendo do **Tipo de Uso** especificado para a coluna na página **Colunas de Entrada** do **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="e2b01-130">These properties are read-only or read/write depending on the **Usage Type** specified for the column on the **Input Columns** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="e2b01-131">Uma propriedade **\<column>_IsNull** para cada coluna de entrada selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-131">A **\<column>_IsNull** property for each selected input column.</span></span> <span data-ttu-id="e2b01-132">Essa propriedade também é somente leitura ou de leitura/gravação, dependendo do **Tipo de Uso** especificado para a coluna.</span><span class="sxs-lookup"><span data-stu-id="e2b01-132">This property is also read-only or read/write depending on the **Usage Type** specified for the column.</span></span>

-   <span data-ttu-id="e2b01-133">Um método **DirectRowTo\<outputbuffer>** para cada saída configurada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-133">A **DirectRowTo\<outputbuffer>** method for each configured output.</span></span> <span data-ttu-id="e2b01-134">Você usará esses métodos ao filtrar linhas para uma das várias saídas no mesmo `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-134">You will use these methods when filtering rows to one of several outputs in the same `ExclusionGroup`.</span></span>

-   <span data-ttu-id="e2b01-135">Uma função `NextRow` para obter a próxima linha de entrada e uma função `EndOfRowset` para determinar se o último buffer de dados foi processado.</span><span class="sxs-lookup"><span data-stu-id="e2b01-135">A `NextRow` function to get the next input row, and an `EndOfRowset` function to determine whether the last buffer of data has been processed.</span></span> <span data-ttu-id="e2b01-136">Em geral, você não precisa dessas funções ao usar os métodos de processamento de entrada implementados na classe base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-136">You typically do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span> <span data-ttu-id="e2b01-137">A próxima seção fornece mais informações sobre a classe base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-137">The next section provides more information about the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="e2b01-138">O que o item de projeto ComponentWrapper fornece</span><span class="sxs-lookup"><span data-stu-id="e2b01-138">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="e2b01-139">O item de projeto ComponentWrapper contém uma classe nomeada `UserComponent` que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="e2b01-139">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="e2b01-140">A classe `ScriptMain` na qual você escreve seu código personalizado, por sua vez, deriva de `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-140">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="e2b01-141">A classe `UserComponent` contém os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="e2b01-141">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="e2b01-142">Uma implementação substituída do método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-142">An overridden implementation of the `ProcessInput` method.</span></span> <span data-ttu-id="e2b01-143">Esse é o método que o mecanismo de fluxo de dados chama em seguida no tempo de execução, depois do método `PreExecute`, e ele pode ser chamado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="e2b01-143">This is the method that the data flow engine calls next at run time after the `PreExecute` method, and it may be called multiple times.</span></span> <span data-ttu-id="e2b01-144">`ProcessInput`transfere o processamento para o método \*\* \<inputbuffer> _ProcessInput\*\* .</span><span class="sxs-lookup"><span data-stu-id="e2b01-144">`ProcessInput` hands off processing to the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="e2b01-145">Depois, o método `ProcessInput` verifica se o buffer de entrada chegou ao final e, em caso positivo, chama o método substituível `FinishOutputs` e o método particular `MarkOutputsAsFinished`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-145">Then the `ProcessInput` method checks for the end of the input buffer and, if the end of the buffer has been reached, calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="e2b01-146">O `MarkOutputsAsFinished` método então chama `SetEndOfRowset` o último buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="e2b01-146">The `MarkOutputsAsFinished` method then calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="e2b01-147">Uma implementação substituível do método **\<inputbuffer>_ProcessInput**.</span><span class="sxs-lookup"><span data-stu-id="e2b01-147">An overridable implementation of the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="e2b01-148">Essa implementação padrão simplesmente executa um loop em cada linha de entrada e chama **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="e2b01-148">This default implementation simply loops through each input row and calls **\<inputbuffer>_ProcessInputRow**.</span></span>

-   <span data-ttu-id="e2b01-149">Uma implementação substituível do método **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="e2b01-149">An overridable implementation of the **\<inputbuffer>_ProcessInputRow** method.</span></span> <span data-ttu-id="e2b01-150">A implementação padrão é vazia.</span><span class="sxs-lookup"><span data-stu-id="e2b01-150">The default implementation is empty.</span></span> <span data-ttu-id="e2b01-151">Esse é o método que, em geral, você substituirá para escrever seu código de processamento de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="e2b01-151">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="e2b01-152">O que seu código personalizado deve fazer</span><span class="sxs-lookup"><span data-stu-id="e2b01-152">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="e2b01-153">Você pode usar os seguintes métodos para processar a entrada na classe `ScriptMain`:</span><span class="sxs-lookup"><span data-stu-id="e2b01-153">You can use the following methods to process input in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="e2b01-154">Substitua o **\<inputbuffer>_ProcessInputRow** para processar os dados em cada linha de entrada conforme ela passa.</span><span class="sxs-lookup"><span data-stu-id="e2b01-154">Override **\<inputbuffer>_ProcessInputRow** to process the data in each input row as it passes through.</span></span>

-   <span data-ttu-id="e2b01-155">Só substitua o **\<inputbuffer>_ProcessInput** se você precisar fazer algo adicional enquanto executa um loop em linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-155">Override **\<inputbuffer>_ProcessInput** only if you have to do something additional while looping through input rows.</span></span> <span data-ttu-id="e2b01-156">(Por exemplo, você precisa testar para `EndOfRowset` para executar alguma outra ação depois que todas as linhas tiverem sido processadas.) Chame \*\* \<inputbuffer> _ProcessInputRow\*\* para executar o processamento de linha.</span><span class="sxs-lookup"><span data-stu-id="e2b01-156">(For example, you have to test for `EndOfRowset` to take some other action after all rows have been processed.) Call **\<inputbuffer>_ProcessInputRow** to perform the row processing.</span></span>

-   <span data-ttu-id="e2b01-157">Substitua o `FinishOutputs` se precisar fazer algo nas saídas antes de seu fechamento.</span><span class="sxs-lookup"><span data-stu-id="e2b01-157">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="e2b01-158">O método `ProcessInput` garante que esses métodos sejam chamados nos momentos apropriados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-158">The `ProcessInput` method ensures that these methods are called at the appropriate times.</span></span>

### <a name="processing-outputs"></a><span data-ttu-id="e2b01-159">Processando saídas</span><span class="sxs-lookup"><span data-stu-id="e2b01-159">Processing Outputs</span></span>
 <span data-ttu-id="e2b01-160">Componentes Script configurados como origens ou transformações têm uma ou mais saídas.</span><span class="sxs-lookup"><span data-stu-id="e2b01-160">Script components configured as sources or transformations have one or more outputs.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="e2b01-161">O que o item de projeto BufferWrapper fornece</span><span class="sxs-lookup"><span data-stu-id="e2b01-161">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="e2b01-162">Para cada saída configurada, o item de projeto BufferWrapper contém uma classe que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> e possui o mesmo nome que a saída.</span><span class="sxs-lookup"><span data-stu-id="e2b01-162">For each output that you have configured, the BufferWrapper project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the output.</span></span> <span data-ttu-id="e2b01-163">Cada classe de buffer de entrada contém as seguintes propriedades e métodos:</span><span class="sxs-lookup"><span data-stu-id="e2b01-163">Each input buffer class contains the following properties and methods:</span></span>

-   <span data-ttu-id="e2b01-164">Propriedades do acessador nomeado, digitado, somente gravação para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="e2b01-164">Named, typed, write-only accessor properties for each output column.</span></span>

-   <span data-ttu-id="e2b01-165">Uma propriedade \*\* \<column> _IsNull\*\* somente gravação para cada coluna de saída selecionada que você pode usar para definir o valor da coluna como `null` .</span><span class="sxs-lookup"><span data-stu-id="e2b01-165">A write-only **\<column>_IsNull** property for each selected output column that you can use to set the column value to `null`.</span></span>

-   <span data-ttu-id="e2b01-166">Um método `AddRow` para adicionar uma linha nova vazia ao buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="e2b01-166">An `AddRow` method to add an empty new row to the output buffer.</span></span>

-   <span data-ttu-id="e2b01-167">Um método `SetEndOfRowset` para notificar o mecanismo de fluxo de dados buffers de que dados não são mais esperados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-167">A `SetEndOfRowset` method to let the data flow engine know that no more buffers of data are expected.</span></span> <span data-ttu-id="e2b01-168">Também há uma função `EndOfRowset` para determinar se o buffer atual é o último buffer de dados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-168">There is also an `EndOfRowset` function to determine whether the current buffer is the last buffer of data.</span></span> <span data-ttu-id="e2b01-169">Geralmente, você não precisa dessas funções quando usa os métodos de processamento de entrada implementados na `UserComponent` classe base.</span><span class="sxs-lookup"><span data-stu-id="e2b01-169">You generally do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="e2b01-170">O que o item de projeto ComponentWrapper fornece</span><span class="sxs-lookup"><span data-stu-id="e2b01-170">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="e2b01-171">O item de projeto ComponentWrapper contém uma classe nomeada `UserComponent` que deriva de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="e2b01-171">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="e2b01-172">A classe `ScriptMain` na qual você escreve seu código personalizado, por sua vez, deriva de `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-172">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="e2b01-173">A classe `UserComponent` contém os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="e2b01-173">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="e2b01-174">Uma implementação substituída do método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-174">An overridden implementation of the `PrimeOutput` method.</span></span> <span data-ttu-id="e2b01-175">O mecanismo de fluxo de dados chama esse método antes do `ProcessInput` em tempo de execução e ele é chamado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="e2b01-175">The data flow engine calls this method before `ProcessInput` at run time, and it is only called one time.</span></span> <span data-ttu-id="e2b01-176">`PrimeOutput` entrega o processamento para o método `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-176">`PrimeOutput` hands off processing to the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="e2b01-177">Depois, se o componente for uma origem (ou seja, se o componente não possuir entradas), o `PrimeOutput` chamará o método `FinishOutputs` substituível e o método `MarkOutputsAsFinished` particular.</span><span class="sxs-lookup"><span data-stu-id="e2b01-177">Then, if the component is a source (that is, the component has no inputs), `PrimeOutput` calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="e2b01-178">O método `MarkOutputsAsFinished` chama o `SetEndOfRowset` no último buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="e2b01-178">The `MarkOutputsAsFinished` method calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="e2b01-179">Uma implementação substituível do método `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-179">An overridable implementation of the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="e2b01-180">A implementação padrão é vazia.</span><span class="sxs-lookup"><span data-stu-id="e2b01-180">The default implementation is empty.</span></span> <span data-ttu-id="e2b01-181">Esse é o método que, em geral, você substituirá para escrever seu código de processamento de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="e2b01-181">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="e2b01-182">O que seu código personalizado deve fazer</span><span class="sxs-lookup"><span data-stu-id="e2b01-182">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="e2b01-183">Você pode usar os seguintes métodos para processar saídas na classe `ScriptMain`:</span><span class="sxs-lookup"><span data-stu-id="e2b01-183">You can use the following methods to process outputs in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="e2b01-184">Substitua `CreateNewOutputRows` apenas quando você puder adicionar e preencher linhas de saída antes de processar linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-184">Override `CreateNewOutputRows` only when you can add and populate output rows before processing input rows.</span></span> <span data-ttu-id="e2b01-185">Por exemplo, você pode usar o `CreateNewOutputRows` em uma origem. Mas em uma transformação com saídas assíncronas, chame o `AddRow` durante ou depois do processamento de dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="e2b01-185">For example, you can use `CreateNewOutputRows` in a source, but in a transformation with asynchronous outputs, you should call `AddRow` during or after the processing of input data.</span></span>

-   <span data-ttu-id="e2b01-186">Substitua o `FinishOutputs` se precisar fazer algo nas saídas antes de seu fechamento.</span><span class="sxs-lookup"><span data-stu-id="e2b01-186">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="e2b01-187">O método `PrimeOutput` garante que esses métodos sejam chamados nos momentos apropriados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-187">The `PrimeOutput` method ensures that these methods are called at the appropriate times.</span></span>

## <a name="postexecute-method"></a><span data-ttu-id="e2b01-188">Método PostExecute</span><span class="sxs-lookup"><span data-stu-id="e2b01-188">PostExecute Method</span></span>
 <span data-ttu-id="e2b01-189">Substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> sempre que houver processamento a ser executado uma só vez após o processamento das linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-189">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only after you have processed the rows of data.</span></span> <span data-ttu-id="e2b01-190">Por exemplo, em uma origem, talvez você queira fechar o `System.Data.SqlClient.SqlDataReader` usado para carregar dados no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-190">For example, in a source, you may want to close the `System.Data.SqlClient.SqlDataReader` that you have used to load data into the data flow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e2b01-191">A coleção de `ReadWriteVariables` só está disponível no método `PostExecute`.</span><span class="sxs-lookup"><span data-stu-id="e2b01-191">The collection of `ReadWriteVariables` is available only in the `PostExecute` method.</span></span> <span data-ttu-id="e2b01-192">Portanto, não será possível incrementar diretamente o valor de uma variável de pacote ao processar cada linha de dados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-192">Therefore you cannot directly increment the value of a package variable as you process each row of data.</span></span> <span data-ttu-id="e2b01-193">Em vez disso, aumente o valor de uma variável local e defina o valor da variável de pacote como o valor da variável local no `PostExecute` método depois que todos os dados tiverem sido processados.</span><span class="sxs-lookup"><span data-stu-id="e2b01-193">Instead, increment the value of a local variable, and set the value of the package variable to the value of the local variable in the `PostExecute` method after all data has been processed.</span></span>

## <a name="releaseconnections-method"></a><span data-ttu-id="e2b01-194">Método ReleaseConnections</span><span class="sxs-lookup"><span data-stu-id="e2b01-194">ReleaseConnections Method</span></span>
 <span data-ttu-id="e2b01-195">Origens e destinos geralmente precisam se conectar a uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="e2b01-195">Sources and destinations typically must connect to an external data source.</span></span> <span data-ttu-id="e2b01-196">Substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> para fechar e liberar a conexão aberta anteriormente no método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2b01-196">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to close and release the connection that you have opened previously in the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method.</span></span>

```vb
    Dim connMgr As IDTSConnectionManager100
...
    Public Overrides Sub ReleaseConnections()

        connMgr.ReleaseConnection(sqlConn)

    End Sub
```

```csharp
IDTSConnectionManager100 connMgr;

public override void ReleaseConnections()
{

    connMgr.ReleaseConnection(sqlConn);

}
```

<span data-ttu-id="e2b01-197">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e2b01-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e2b01-198">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="e2b01-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e2b01-199">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="e2b01-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e2b01-200">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="e2b01-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2b01-201">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2b01-201">See Also</span></span>
 <span data-ttu-id="e2b01-202">[Configurando o componente script no editor de componentes de script](configuring-the-script-component-in-the-script-component-editor.md) [codificando e Depurando o componente Script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span><span class="sxs-lookup"><span data-stu-id="e2b01-202">[Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span></span>


