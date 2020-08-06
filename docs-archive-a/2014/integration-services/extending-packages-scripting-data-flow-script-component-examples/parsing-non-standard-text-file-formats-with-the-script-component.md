---
title: Analisar formatos de arquivo de texto não padrão com o componente Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- text file reading [Integration Services]
- Script component [Integration Services], non-standard text file formats
- transformations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: 1fda034d-09e4-4647-9a9f-e8d508c2cc8f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a0ca1a0d10bdad40d39a366864a07d2b0a61d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679434"
---
# <a name="parsing-non-standard-text-file-formats-with-the-script-component"></a><span data-ttu-id="477b0-102">Analisando formatos de arquivo de texto fora do padrão com o componente Script</span><span class="sxs-lookup"><span data-stu-id="477b0-102">Parsing Non-Standard Text File Formats with the Script Component</span></span>
  <span data-ttu-id="477b0-103">Quando seus dados de origem estiverem dispostos em um formato não padrão, talvez seja mais conveniente consolidar toda a sua lógica de análise em um único script do que reunir várias transformações [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para chegar ao mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="477b0-103">When your source data is arranged in a non-standard format, you may find it more convenient to consolidate all your parsing logic in a single script than to chain together multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations to achieve the same result.</span></span>  
  
 [<span data-ttu-id="477b0-104">Exemplo 1: analisar registros delimitados por linha</span><span class="sxs-lookup"><span data-stu-id="477b0-104">Example 1: Parsing Row-Delimited Records</span></span>](#example1)  
  
 [<span data-ttu-id="477b0-105">Exemplo 2: dividir registros pai e filho</span><span class="sxs-lookup"><span data-stu-id="477b0-105">Example 2: Splitting Parent and Child Records</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="477b0-106">Se desejar criar um componente que possa ser reutilizado mais facilmente em várias tarefas de fluxo de dados e em vários pacotes, procure utilizar o código deste exemplo de componente Script como o ponto inicial de um componente de fluxo de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="477b0-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="477b0-107">Para obter mais informações, consulte [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="477b0-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
##  <a name="example-1-parsing-row-delimited-records"></a><a name="example1"></a> <span data-ttu-id="477b0-108">Exemplo 1: analisar registros delimitados por linha</span><span class="sxs-lookup"><span data-stu-id="477b0-108">Example 1: Parsing Row-Delimited Records</span></span>  
 <span data-ttu-id="477b0-109">Este exemplo mostra como utilizar um arquivo de texto em que cada coluna de dados aparece em uma linha separada e analisá-lo em uma tabela de destino usando o componente Script.</span><span class="sxs-lookup"><span data-stu-id="477b0-109">This example shows how to take a text file in which each column of data appears on a separate line and parse it into a destination table by using the Script component.</span></span>  
  
 <span data-ttu-id="477b0-110">Para obter mais informações sobre como configurar o componente Script para uso como uma transformação no fluxo de dados, consulte [criando uma transformação síncrona com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)e [criando uma transformação assíncrona com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="477b0-110">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="477b0-111">Para configurar esse exemplo de componente Script</span><span class="sxs-lookup"><span data-stu-id="477b0-111">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="477b0-112">Crie e salve um arquivo de texto nomeado **rowdelimiteddata.txt** contendo os seguintes dados de origem:</span><span class="sxs-lookup"><span data-stu-id="477b0-112">Create and save a text file named **rowdelimiteddata.txt** that contains the following source data:</span></span>  
  
    ```  
    FirstName: Nancy  
    LastName: Davolio  
    Title: Sales Representative  
    City: Seattle  
    StateProvince: WA  
  
    FirstName: Andrew  
    LastName: Fuller  
    Title: Vice President, Sales  
    City: Tacoma  
    StateProvince: WA  
  
    FirstName: Steven  
    LastName: Buchanan  
    Title: Sales Manager  
    City: London  
    StateProvince:  
  
    ```  
  
2.  <span data-ttu-id="477b0-113">Abra o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477b0-113">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="477b0-114">Selecione um banco de dados de destino e abra uma nova janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="477b0-114">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="477b0-115">Na janela de consulta, execute o seguinte script para criar a tabela de destino:</span><span class="sxs-lookup"><span data-stu-id="477b0-115">In the query window, execute the following script to create the destination table:</span></span>  
  
    ```  
    create table RowDelimitedData  
    (  
    FirstName varchar(32),  
    LastName varchar(32),  
    Title varchar(32),  
    City varchar(32),  
    StateProvince varchar(32)  
    )  
  
    ```  
  
4.  <span data-ttu-id="477b0-116">Abra o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] e crie um novo pacote de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nomeado ParseRowDelim.dtsx.</span><span class="sxs-lookup"><span data-stu-id="477b0-116">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named ParseRowDelim.dtsx.</span></span>  
  
5.  <span data-ttu-id="477b0-117">Adicione um gerenciador de conexões de arquivos simples ao pacote, nomeie-o como RowDelimitedData e configure-o para conectá-lo ao arquivo rowdelimiteddata.txt criado em uma etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="477b0-117">Add a Flat File connection manager to the package, name it RowDelimitedData, and configure it to connect to the rowdelimiteddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="477b0-118">Adicione um gerenciador de conexões OLE DB ao pacote e configure-o para conectá-lo à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ao banco de dados em que você criou a tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="477b0-118">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination table.</span></span>  
  
7.  <span data-ttu-id="477b0-119">Adicione uma tarefa de Fluxo de Dados ao pacote e clique na guia **Fluxo de Dados** do Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="477b0-119">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="477b0-120">Adicione uma Fonte de Arquivo Simples ao fluxo de dados e configure-a para usar o gerenciador de conexões do RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="477b0-120">Add a Flat File Source to the data flow and configure it to use the RowDelimitedData connection manager.</span></span> <span data-ttu-id="477b0-121">Na página **Colunas** do **Editor de Fonte de Arquivo Simples**, selecione a única coluna externa disponível.</span><span class="sxs-lookup"><span data-stu-id="477b0-121">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="477b0-122">Adicione um Componente Script ao fluxo de dados e configure-o como uma transformação.</span><span class="sxs-lookup"><span data-stu-id="477b0-122">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="477b0-123">Conecte a saída da Fonte de Arquivo Simples ao Componente Script.</span><span class="sxs-lookup"><span data-stu-id="477b0-123">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="477b0-124">Clique duas vezes no componente Script para exibir o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="477b0-124">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="477b0-125">Na página **Colunas de Entrada** do **Editor de Transformação Scripts**, selecione a única coluna de entrada disponível.</span><span class="sxs-lookup"><span data-stu-id="477b0-125">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="477b0-126">Na página **entradas e saídas** do editor de **transformação scripts**, selecione saída 0 e defina `SynchronousInputID` como nenhum.</span><span class="sxs-lookup"><span data-stu-id="477b0-126">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0 and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="477b0-127">Crie 5 colunas de saída, todas com tipo cadeia de caracteres [DT_STR] com comprimento 32:</span><span class="sxs-lookup"><span data-stu-id="477b0-127">Create 5 output columns, all of type string [DT_STR] with a length of 32:</span></span>  
  
    -   <span data-ttu-id="477b0-128">Nome</span><span class="sxs-lookup"><span data-stu-id="477b0-128">FirstName</span></span>  
  
    -   <span data-ttu-id="477b0-129">LastName</span><span class="sxs-lookup"><span data-stu-id="477b0-129">LastName</span></span>  
  
    -   <span data-ttu-id="477b0-130">Title</span><span class="sxs-lookup"><span data-stu-id="477b0-130">Title</span></span>  
  
    -   <span data-ttu-id="477b0-131">City</span><span class="sxs-lookup"><span data-stu-id="477b0-131">City</span></span>  
  
    -   <span data-ttu-id="477b0-132">StateProvince</span><span class="sxs-lookup"><span data-stu-id="477b0-132">StateProvince</span></span>  
  
13. <span data-ttu-id="477b0-133">Na página **script** do editor de **transformação scripts**, clique em **Editar script** e insira o código mostrado na `ScriptMain` classe do exemplo.</span><span class="sxs-lookup"><span data-stu-id="477b0-133">On the **Script** page of the **Script Transformation Editor**, click **Edit Script** and enter the code shown in the `ScriptMain` class of the example.</span></span> <span data-ttu-id="477b0-134">Feche o ambiente de desenvolvimento de scripts e o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="477b0-134">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
14. <span data-ttu-id="477b0-135">Adicione um Destino de SQL Server ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="477b0-135">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="477b0-136">Configure-o para usar o gerenciador de conexões do OLE DB e a tabela RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="477b0-136">Configure it to use the OLE DB connection manager and the RowDelimitedData table.</span></span> <span data-ttu-id="477b0-137">Conecte a saída do Componente Script a este destino.</span><span class="sxs-lookup"><span data-stu-id="477b0-137">Connect the output of the Script Component to this destination.</span></span>  
  
15. <span data-ttu-id="477b0-138">Execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="477b0-138">Run the package.</span></span> <span data-ttu-id="477b0-139">Depois da conclusão do pacote, examine os registros na tabela de destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477b0-139">After the package has finished, examine the records in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination table.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Dim columnName As String  
    Dim columnValue As String  
  
    ' Check for an empty row.  
    If Row.Column0.Trim.Length > 0 Then  
        columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"))  
        ' Check for an empty value after the colon.  
        If Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd.Length > 1 Then  
            ' Extract the column value from after the colon and space.  
            columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2)  
            Select Case columnName  
                Case "FirstName"  
                    ' The FirstName value indicates a new record.  
                    Me.Output0Buffer.AddRow()  
                    Me.Output0Buffer.FirstName = columnValue  
                Case "LastName"  
                    Me.Output0Buffer.LastName = columnValue  
                Case "Title"  
                    Me.Output0Buffer.Title = columnValue  
                Case "City"  
                    Me.Output0Buffer.City = columnValue  
                Case "StateProvince"  
                    Me.Output0Buffer.StateProvince = columnValue  
            End Select  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
        string columnName;  
        string columnValue;  
  
        // Check for an empty row.  
        if (Row.Column0.Trim().Length > 0)  
        {  
            columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"));  
            // Check for an empty value after the colon.  
            if (Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd().Length > 1)  
            // Extract the column value from after the colon and space.  
            {  
                columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2);  
                switch (columnName)  
                {  
                    case "FirstName":  
                        // The FirstName value indicates a new record.  
                        this.Output0Buffer.AddRow();  
                        this.Output0Buffer.FirstName = columnValue;  
                        break;  
                    case "LastName":  
                        this.Output0Buffer.LastName = columnValue;  
                        break;  
                    case "Title":  
                        this.Output0Buffer.Title = columnValue;  
                        break;  
                    case "City":  
                        this.Output0Buffer.City = columnValue;  
                        break;  
                    case "StateProvince":  
                        this.Output0Buffer.StateProvince = columnValue;  
                        break;  
                }  
            }  
        }  
  
    }  
```  
  
##  <a name="example-2-splitting-parent-and-child-records"></a><a name="example2"></a> <span data-ttu-id="477b0-140">Exemplo 2: dividir registros pai e filho</span><span class="sxs-lookup"><span data-stu-id="477b0-140">Example 2: Splitting Parent and Child Records</span></span>  
 <span data-ttu-id="477b0-141">Este exemplo mostra como utilizar um arquivo de texto, em que uma linha delimitadora precede uma linha de registro pai, que é seguida de um número indefinido de linhas de registro filho, e analisa-as em tabelas de destino pai e filho, adequadamente normalizadas, através do componente Script.</span><span class="sxs-lookup"><span data-stu-id="477b0-141">This example shows how to take a text file, in which a separator row precedes a parent record row that is followed by an indefinite number of child record rows, and parse it into properly normalized parent and child destination tables by using the Script component.</span></span> <span data-ttu-id="477b0-142">Esse exemplo simples pode ser facilmente adaptado para arquivos de origem que utilizam mais de uma linha ou coluna para cada registro pai e filho, desde que exista uma forma de identificar o início e o fim de cada registro.</span><span class="sxs-lookup"><span data-stu-id="477b0-142">This simple example could easily be adapted for source files that use more than one row or column for each parent and child record, as long as there is some way to identify the beginning and end of each record.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="477b0-143">Esse exemplo é utilizado apenas para fins de demonstração.</span><span class="sxs-lookup"><span data-stu-id="477b0-143">This sample is intended for demonstration purposes only.</span></span> <span data-ttu-id="477b0-144">Se você executar o exemplo mais de uma vez, ele inserirá valores de chave duplicados na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="477b0-144">If you run the sample more than once, it inserts duplicate key values into the destination table.</span></span>  
  
 <span data-ttu-id="477b0-145">Para obter mais informações sobre como configurar o componente Script para uso como uma transformação no fluxo de dados, consulte [criando uma transformação síncrona com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)e [criando uma transformação assíncrona com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="477b0-145">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="477b0-146">Para configurar esse exemplo de componente Script</span><span class="sxs-lookup"><span data-stu-id="477b0-146">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="477b0-147">Crie e salve um arquivo de texto nomeado **parentchilddata.txt** contendo os seguintes dados de origem:</span><span class="sxs-lookup"><span data-stu-id="477b0-147">Create and save a text file named **parentchilddata.txt** that contains the following source data:</span></span>  
  
    ```  
    **********  
    PARENT 1 DATA  
    child 1 data  
    child 2 data  
    child 3 data  
    child 4 data  
    **********  
    PARENT 2 DATA  
    child 5 data  
    child 6 data  
    child 7 data  
    child 8 data  
    **********  
  
    ```  
  
2.  <span data-ttu-id="477b0-148">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477b0-148">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="477b0-149">Selecione um banco de dados de destino e abra uma nova janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="477b0-149">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="477b0-150">Na janela de consulta, execute o seguinte script para criar as tabelas de destino:</span><span class="sxs-lookup"><span data-stu-id="477b0-150">In the query window, execute the following script to create the destination tables:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[Parents]([ParentID] [int] NOT NULL,  
    [ParentRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Parents] PRIMARY KEY CLUSTERED   
    ([ParentID] ASC))  
    GO  
    CREATE TABLE [dbo].[Children]([ChildID] [int] NOT NULL,  
    [ParentID] [int] NOT NULL,  
    [ChildRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Children] PRIMARY KEY CLUSTERED   
    ([ChildID] ASC))  
    GO  
    ALTER TABLE [dbo].[Children] ADD CONSTRAINT [FK_Children_Parents] FOREIGN KEY([ParentID])  
    REFERENCES [dbo].[Parents] ([ParentID])  
  
    ```  
  
4.  <span data-ttu-id="477b0-151">Abra o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e crie um novo pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nomeado SplitParentChild.dtsx.</span><span class="sxs-lookup"><span data-stu-id="477b0-151">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named SplitParentChild.dtsx.</span></span>  
  
5.  <span data-ttu-id="477b0-152">Adicione um gerenciador de conexões de arquivos simples ao pacote, nomeie-o como ParentChildData e configure-o para conectá-lo ao arquivo parentchilddata.txt criado em uma etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="477b0-152">Add a Flat File connection manager to the package, name it ParentChildData, and configure it to connect to the parentchilddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="477b0-153">Adicione um gerenciador de conexões OLE DB ao pacote e configure-o para conectar-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e ao banco de dados em que você criou as tabelas de destino.</span><span class="sxs-lookup"><span data-stu-id="477b0-153">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination tables.</span></span>  
  
7.  <span data-ttu-id="477b0-154">Adicione uma tarefa de Fluxo de Dados ao pacote e clique na guia **Fluxo de Dados** do Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="477b0-154">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="477b0-155">Adicione uma Fonte de Arquivo Simples ao fluxo de dados e configure-a para usar o gerenciador de conexões do ParentChildData.</span><span class="sxs-lookup"><span data-stu-id="477b0-155">Add a Flat File Source to the data flow and configure it to use the ParentChildData connection manager.</span></span> <span data-ttu-id="477b0-156">Na página **Colunas** do **Editor de Fonte de Arquivo Simples**, selecione a única coluna externa disponível.</span><span class="sxs-lookup"><span data-stu-id="477b0-156">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="477b0-157">Adicione um Componente Script ao fluxo de dados e configure-o como uma transformação.</span><span class="sxs-lookup"><span data-stu-id="477b0-157">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="477b0-158">Conecte a saída da Fonte de Arquivo Simples ao Componente Script.</span><span class="sxs-lookup"><span data-stu-id="477b0-158">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="477b0-159">Clique duas vezes no componente Script para exibir o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="477b0-159">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="477b0-160">Na página **Colunas de Entrada** do **Editor de Transformação Scripts**, selecione a única coluna de entrada disponível.</span><span class="sxs-lookup"><span data-stu-id="477b0-160">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="477b0-161">Na página **entradas e saídas** do editor de **transformação scripts**, selecione saída 0, renomeie para ParentRecords e defina seu `SynchronousInputID` como nenhum.</span><span class="sxs-lookup"><span data-stu-id="477b0-161">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0, rename it to ParentRecords, and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="477b0-162">Crie 2 colunas de saída:</span><span class="sxs-lookup"><span data-stu-id="477b0-162">Create 2 output columns:</span></span>  
  
    -   <span data-ttu-id="477b0-163">ParentID (a chave primária), de tipo inteiro assinado de quatro bytes [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="477b0-163">ParentID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="477b0-164">ParentRecord, de cadeia de caracteres de tipo [DT_STR] com comprimento de 32.</span><span class="sxs-lookup"><span data-stu-id="477b0-164">ParentRecord, of type string [DT_STR] with a length of 32.</span></span>  
  
13. <span data-ttu-id="477b0-165">Crie uma segunda saída e nomeie-a como ChildRecords.</span><span class="sxs-lookup"><span data-stu-id="477b0-165">Create a second output and name it ChildRecords.</span></span> <span data-ttu-id="477b0-166">O `SynchronousInputID` da nova saída já está definido como Nenhum.</span><span class="sxs-lookup"><span data-stu-id="477b0-166">The `SynchronousInputID` of the new output is already set to None.</span></span> <span data-ttu-id="477b0-167">Crie 3 colunas de saída:</span><span class="sxs-lookup"><span data-stu-id="477b0-167">Create 3 output columns:</span></span>  
  
    -   <span data-ttu-id="477b0-168">ChildID (a chave primária), de tipo inteiro assinado de quatro bytes [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="477b0-168">ChildID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="477b0-169">ParentID (a chave estrangeira), também de tipo inteiro assinado de quatro bytes [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="477b0-169">ParentID (the foreign key), also of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="477b0-170">ChildRecord, de cadeia de caracteres de tipo [DT_STR] com comprimento de 50</span><span class="sxs-lookup"><span data-stu-id="477b0-170">ChildRecord, of type string [DT_STR] with a length of 50</span></span>  
  
14. <span data-ttu-id="477b0-171">Na página **Script** do **Editor de Transformação Scripts**, clique em **Editar Script**.</span><span class="sxs-lookup"><span data-stu-id="477b0-171">On the **Script** page of the **Script Transformation Editor**, click **Edit Script**.</span></span> <span data-ttu-id="477b0-172">Na classe `ScriptMain`, digite o código mostrado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="477b0-172">In the `ScriptMain` class, enter the code shown in the example.</span></span> <span data-ttu-id="477b0-173">Feche o ambiente de desenvolvimento de scripts e o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="477b0-173">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
15. <span data-ttu-id="477b0-174">Adicione um Destino de SQL Server ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="477b0-174">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="477b0-175">Conecte a saída de ParentRecords do Componente Script a esse destino. Configure-o para usar o gerenciador de conexões OLE DB e a tabela Pais.</span><span class="sxs-lookup"><span data-stu-id="477b0-175">Connect the ParentRecords output of the Script Component to this destination.Configure it to use the OLE DB connection manager and the Parents table.</span></span>  
  
16. <span data-ttu-id="477b0-176">Adicione outro Destino de SQL Server ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="477b0-176">Add another SQL Server Destination to the data flow.</span></span> <span data-ttu-id="477b0-177">Conecte a saída ChildRecords do Componente Script a esse destino.</span><span class="sxs-lookup"><span data-stu-id="477b0-177">Connect the ChildRecords output of the Script Component to this destination.</span></span> <span data-ttu-id="477b0-178">Configure-o para usar o gerenciador de conexões OLE DB e a tabela Filhos.</span><span class="sxs-lookup"><span data-stu-id="477b0-178">Configure it to use the OLE DB connection manager and the Children table.</span></span>  
  
17. <span data-ttu-id="477b0-179">Execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="477b0-179">Run the package.</span></span> <span data-ttu-id="477b0-180">Depois da conclusão do pacote, examine os registros pai e filho nas duas tabelas de destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477b0-180">After the package has finished, examine the parent and child records in the two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination tables.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Static nextRowIsParent As Boolean = False  
    Static parentCounter As Integer = 0  
    Static childCounter As Integer = 0  
  
    ' If current row starts with separator characters,  
    '  then following row contains new parent record.  
    If Row.Column0.StartsWith("***") Then  
        nextRowIsParent = True  
    Else  
        If nextRowIsParent Then  
            ' Current row contains parent record.  
            parentCounter += 1  
            Me.ParentRecordsBuffer.AddRow()  
            Me.ParentRecordsBuffer.ParentID = parentCounter  
            Me.ParentRecordsBuffer.ParentRecord = Row.Column0  
            nextRowIsParent = False  
        Else  
            ' Current row contains child record.  
            childCounter += 1  
            Me.ChildRecordsBuffer.AddRow()  
            Me.ChildRecordsBuffer.ChildID = childCounter  
            Me.ChildRecordsBuffer.ParentID = parentCounter  
            Me.ChildRecordsBuffer.ChildRecord = Row.Column0  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
    int static_Input0_ProcessInputRow_childCounter = 0;  
    int static_Input0_ProcessInputRow_parentCounter = 0;  
    bool static_Input0_ProcessInputRow_nextRowIsParent = false;  
  
        // If current row starts with separator characters,   
        // then following row contains new parent record.   
        if (Row.Column0.StartsWith("***"))  
        {  
            static_Input0_ProcessInputRow_nextRowIsParent = true;  
        }  
        else  
        {  
            if (static_Input0_ProcessInputRow_nextRowIsParent)  
            {  
                // Current row contains parent record.   
                static_Input0_ProcessInputRow_parentCounter += 1;  
                this.ParentRecordsBuffer.AddRow();  
                this.ParentRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ParentRecordsBuffer.ParentRecord = Row.Column0;  
                static_Input0_ProcessInputRow_nextRowIsParent = false;  
            }  
            else  
            {  
                // Current row contains child record.   
                static_Input0_ProcessInputRow_childCounter += 1;  
                this.ChildRecordsBuffer.AddRow();  
                this.ChildRecordsBuffer.ChildID = static_Input0_ProcessInputRow_childCounter;  
                this.ChildRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ChildRecordsBuffer.ChildRecord = Row.Column0;  
            }  
        }  
  
    }  
```  
  
<span data-ttu-id="477b0-181">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="477b0-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="477b0-182">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="477b0-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="477b0-183">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="477b0-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="477b0-184">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="477b0-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477b0-185">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="477b0-185">See Also</span></span>  
 [<span data-ttu-id="477b0-186">Criando uma transformação síncrona com o componente Script</span><span class="sxs-lookup"><span data-stu-id="477b0-186">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)  
 [<span data-ttu-id="477b0-187">Criar uma transformação assíncrona com o componente de Script</span><span class="sxs-lookup"><span data-stu-id="477b0-187">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
  
  
