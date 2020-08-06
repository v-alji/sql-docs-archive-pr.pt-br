---
title: Usar saídas de erro em um componente de fluxo de dados | Microsoft Docs
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
- errors [Integration Services], alternative outputs
- synchronous error outputs [Integration Services]
- alternative error outputs [Integration Services]
- custom data flow components [Integration Services], error outputs
- data flow components [Integration Services], error outputs
- populating error columns [Integration Services]
- redirecting error output [Integration Services]
- error outputs [Integration Services]
- asynchronous error outputs [Integration Services]
ms.assetid: a2a3e7c8-1de2-45b3-97fb-60415d3b0934
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a05a41065c52fadbe7f7fc065771727310e58149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568703"
---
# <a name="using-error-outputs-in-a-data-flow-component"></a><span data-ttu-id="aba46-102">Usando saídas de erro em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="aba46-102">Using Error Outputs in a Data Flow Component</span></span>
  <span data-ttu-id="aba46-103">Os objetos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> especiais chamados saídas de erro podem ser adicionados a componentes para permitir que o componente redirecione linhas que não pode processar durante a execução.</span><span class="sxs-lookup"><span data-stu-id="aba46-103">Special <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects called error outputs can be added to components to let the component redirect rows that it cannot process during execution.</span></span> <span data-ttu-id="aba46-104">Os problemas que um componente pode encontrar são geralmente categorizados como erros ou truncamentos, e são específicos a cada componente.</span><span class="sxs-lookup"><span data-stu-id="aba46-104">The problems a component may encounter are generally categorized as errors or truncations, and are specific to each component.</span></span> <span data-ttu-id="aba46-105">Os componentes que oferecem saídas de erro fornecem aos seus usuários a flexibilidade de lidar com condições de erro filtrando linhas de erro para fora do conjunto de resultados, falhando o componente quando ocorre um problema ou ignorando erros e continuando.</span><span class="sxs-lookup"><span data-stu-id="aba46-105">Components that provide error outputs give users of the component the flexibility to handle error conditions by filtering error rows out of the result set, by failing the component when a problem occurs, or by ignoring errors and continuing.</span></span>  
  
 <span data-ttu-id="aba46-106">Para implementar e dar suporte a saídas de erro em um componente, você deve primeiro definir a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.UsesDispositions%2A> do componente como `true`.</span><span class="sxs-lookup"><span data-stu-id="aba46-106">To implement and support error outputs in a component, you must first set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.UsesDispositions%2A> property of the component to `true`.</span></span> <span data-ttu-id="aba46-107">Em seguida, você deve acrescentar uma saída ao componente que tem sua propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> definida como `true`.</span><span class="sxs-lookup"><span data-stu-id="aba46-107">Then you must add an output to the component that has its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> property set to `true`.</span></span> <span data-ttu-id="aba46-108">Finalmente, o componente deve conter um código que redirecione linhas à saída de erro quando erros ou truncamentos ocorrerem.</span><span class="sxs-lookup"><span data-stu-id="aba46-108">Finally, the component must contain code that redirects rows to the error output when errors or truncations occur.</span></span> <span data-ttu-id="aba46-109">Este tópico cobre essas três etapas e explica as diferenças entre saídas de erro síncronas e assíncronas.</span><span class="sxs-lookup"><span data-stu-id="aba46-109">This topic covers these three steps and explains the differences between synchronous and asynchronous error outputs.</span></span>  
  
## <a name="creating-an-error-output"></a><span data-ttu-id="aba46-110">Criando uma saída de erro</span><span class="sxs-lookup"><span data-stu-id="aba46-110">Creating an Error Output</span></span>  
 <span data-ttu-id="aba46-111">É possível criar uma saída de erro chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100.New%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.OutputCollection%2A>, e configurando a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> da nova saída com `true`.</span><span class="sxs-lookup"><span data-stu-id="aba46-111">You create an error output by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.OutputCollection%2A>, and then setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> property of the new output to `true`.</span></span> <span data-ttu-id="aba46-112">Se a saída for assíncrona, nada mais deve ser feito.</span><span class="sxs-lookup"><span data-stu-id="aba46-112">If the output is asynchronous, nothing else must be done to the output.</span></span> <span data-ttu-id="aba46-113">Se a saída for síncrona e houver outra saída que seja síncrona à mesma entrada, você também deve definir as propriedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExclusionGroup%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="aba46-113">If the output is synchronous, and there is another output that is synchronous to the same input, you must also set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExclusionGroup%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> properties.</span></span> <span data-ttu-id="aba46-114">Ambas as propriedades devem ter os mesmos valores da outra saída, que é síncrona à mesma entrada.</span><span class="sxs-lookup"><span data-stu-id="aba46-114">Both properties should have the same values as the other output that is synchronous to the same input.</span></span> <span data-ttu-id="aba46-115">Se essas propriedades não forem definidas com um valor diferente de zero, as linhas fornecidas pela entrada serão enviadas para as duas saídas que são síncronas à entrada.</span><span class="sxs-lookup"><span data-stu-id="aba46-115">If these properties are not set to a non-zero value, the rows provided by the input are sent to both outputs that are synchronous to the input.</span></span>  
  
 <span data-ttu-id="aba46-116">Quando um componente encontra um erro ou truncamento durante a execução, ele continua baseando-se nas configurações das propriedades <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ErrorRowDisposition%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.TruncationRowDisposition%2A> da entrada ou saída, ou coluna de entrada ou saída, onde ocorreu o erro.</span><span class="sxs-lookup"><span data-stu-id="aba46-116">When a component encounters an error or truncation during execution, it proceeds based on the settings of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ErrorRowDisposition%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.TruncationRowDisposition%2A> properties of the input or output, or input or output column, where the error occurred.</span></span> <span data-ttu-id="aba46-117">O valor dessas propriedades deve ser definido por padrão como <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSRowDisposition.RD_NotUsed>.</span><span class="sxs-lookup"><span data-stu-id="aba46-117">The value of these properties should be set by default to <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSRowDisposition.RD_NotUsed>.</span></span> <span data-ttu-id="aba46-118">Quando a saída de erro do componente é conectada a um componente downstream, essa propriedade é definida pelo usuário do componente e permite que o usuário controle como o componente vai lidar com o erro ou truncamento.</span><span class="sxs-lookup"><span data-stu-id="aba46-118">When the error output of the component is connected to a downstream component, this property is set by the user of the component and lets the user control how the component handles the error or truncation.</span></span>  
  
## <a name="populating-error-columns"></a><span data-ttu-id="aba46-119">Preenchendo colunas de erro</span><span class="sxs-lookup"><span data-stu-id="aba46-119">Populating Error Columns</span></span>  
 <span data-ttu-id="aba46-120">Quando uma saída de erro é criada, a tarefa de fluxo de dados acrescenta duas colunas automaticamente à coleção de colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="aba46-120">When an error output is created, the data flow task automatically adds two columns to the output column collection.</span></span> <span data-ttu-id="aba46-121">Essas colunas são usadas por componentes para especificar a ID da coluna que causou o erro ou truncamento, e fornecer o código de erro específico do componente.</span><span class="sxs-lookup"><span data-stu-id="aba46-121">These columns are used by components to specify the ID of the column that caused the error or truncation, and to provide the component-specific error code.</span></span> <span data-ttu-id="aba46-122">Essas colunas são geradas automaticamente, mas os valores contidos nas colunas devem ser definidos pelo componente.</span><span class="sxs-lookup"><span data-stu-id="aba46-122">These columns are generated automatically, but the values contained in the columns must be set by the component.</span></span>  
  
 <span data-ttu-id="aba46-123">O método usado para definir os valores dessas colunas depende se a saída de erro é síncrona ou assíncrona.</span><span class="sxs-lookup"><span data-stu-id="aba46-123">The method used to set the values of these columns depends on whether the error output is synchronous or asynchronous.</span></span> <span data-ttu-id="aba46-124">Componentes com saídas síncronas chamam o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A>, discutido em mais detalhes na próxima seção, e fornece o código de erro e os valores da coluna de erro como parâmetros.</span><span class="sxs-lookup"><span data-stu-id="aba46-124">Components with synchronous outputs call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method, discussed in more detail in the next section, and provide the error code and error column values as parameters.</span></span> <span data-ttu-id="aba46-125">Componentes com saídas assíncronas têm duas escolhas para definir os valores dessas colunas.</span><span class="sxs-lookup"><span data-stu-id="aba46-125">Components with asynchronous outputs have two choices for setting the values of these columns.</span></span> <span data-ttu-id="aba46-126">Eles podem chamar o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> do buffer de saída e fornecer os valores, ou localizar as colunas de erro no buffer usando <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> e definir os valores para as colunas diretamente.</span><span class="sxs-lookup"><span data-stu-id="aba46-126">They can either call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method of the output buffer and supply the values, or locate the error columns in the buffer by using <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> and set the values for the columns directly.</span></span> <span data-ttu-id="aba46-127">Entretanto, como os nomes das colunas podem ter sido mudados, ou seu local na coleção de colunas de saída pode ter sido modificado, o último método pode não ser confiável.</span><span class="sxs-lookup"><span data-stu-id="aba46-127">However, because the names of the columns may have been changed, or their location in the output column collection may have been modified, the latter method may not be reliable.</span></span> <span data-ttu-id="aba46-128">O método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> define os valores automaticamente nessas colunas de erro sem ter que localizá-los manualmente.</span><span class="sxs-lookup"><span data-stu-id="aba46-128">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method automatically sets the values in these error columns without having to locate them manually.</span></span>  
  
 <span data-ttu-id="aba46-129">Se você precisar obter a descrição de erro que corresponde a um código de erro específico, você pode usar o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponível através da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> do componente.</span><span class="sxs-lookup"><span data-stu-id="aba46-129">If you need to obtain the error description that corresponds to a specific error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span>  
  
 <span data-ttu-id="aba46-130">Os exemplos de código seguintes mostram um componente que tem uma entrada e duas saídas, inclusive uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="aba46-130">The following code examples show a component that has an input and two outputs, including an error output.</span></span> <span data-ttu-id="aba46-131">O primeiro exemplo mostra como criar uma saída de erro que é síncrona à entrada.</span><span class="sxs-lookup"><span data-stu-id="aba46-131">The first example shows how to create an error output that is synchronous to the input.</span></span> <span data-ttu-id="aba46-132">O segundo exemplo mostra como criar uma saída de erro que é assíncrona.</span><span class="sxs-lookup"><span data-stu-id="aba46-132">The second example shows how to create an error output that is asynchronous.</span></span>  
  
```csharp  
public override void ProvideComponentProperties()  
{  
    // Specify that the component has an error output.  
    ComponentMetaData.UsesDispositions = true;  
    // Create the input.  
    IDTSInput100 input = ComponentMetaData.InputCollection.New();  
    input.Name = "Input";  
    input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed;  
    input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution.";  
  
    // Create the default output.  
    IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
    output.Name = "Output";  
    output.SynchronousInputID = input.ID;  
    output.ExclusionGroup = 1;  
  
    // Create the error output.  
    IDTSOutput100 errorOutput = ComponentMetaData.OutputCollection.New();  
    errorOutput.IsErrorOut = true;  
    errorOutput.Name = "ErrorOutput";  
    errorOutput.SynchronousInputID = input.ID;  
    errorOutput.ExclusionGroup = 1;  
  
}  
```  
  
```vb  
Public  Overrides Sub ProvideComponentProperties()   
  
 ' Specify that the component has an error output.  
 ComponentMetaData.UsesDispositions = True   
  
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New   
  
 ' Create the input.  
 input.Name = "Input"   
 input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed   
 input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution."   
  
 ' Create the default output.  
 Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 output.Name = "Output"   
 output.SynchronousInputID = input.ID   
 output.ExclusionGroup = 1   
  
 ' Create the error output.  
 Dim errorOutput As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 errorOutput.IsErrorOut = True   
 errorOutput.Name = "ErrorOutput"   
 errorOutput.SynchronousInputID = input.ID   
 errorOutput.ExclusionGroup = 1   
  
End Sub  
```  
  
 <span data-ttu-id="aba46-133">O exemplo de código seguinte cria uma saída de erro que é assíncrona.</span><span class="sxs-lookup"><span data-stu-id="aba46-133">The following code example creates an error output that is asynchronous.</span></span>  
  
```csharp  
public override void ProvideComponentProperties()  
{  
    // Specify that the component has an error output.  
    ComponentMetaData.UsesDispositions = true;  
  
    // Create the input.  
    IDTSInput100 input = ComponentMetaData.InputCollection.New();  
    input.Name = "Input";  
    input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed;  
    input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution.";  
  
    // Create the default output.  
    IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
    output.Name = "Output";  
  
    // Create the error output.  
    IDTSOutput100 errorOutput = ComponentMetaData.OutputCollection.New();  
    errorOutput.Name = "ErrorOutput";  
    errorOutput.IsErrorOut = true;  
}  
```  
  
```vb  
Public  Overrides Sub ProvideComponentProperties()   
  
 ' Specify that the component has an error output.  
 ComponentMetaData.UsesDispositions = True   
  
 ' Create the input.  
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New   
  
 ' Create the default output.  
 input.Name = "Input"   
 input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed   
 input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution."   
  
 ' Create the error output.  
 Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 output.Name = "Output"   
 Dim errorOutput As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 errorOutput.Name = "ErrorOutput"   
 errorOutput.IsErrorOut = True   
  
End Sub  
```  
  
## <a name="redirecting-a-row-to-an-error-output"></a><span data-ttu-id="aba46-134">Redirecionando uma linha para uma saída de erro</span><span class="sxs-lookup"><span data-stu-id="aba46-134">Redirecting a Row to an Error Output</span></span>  
 <span data-ttu-id="aba46-135">Depois de acrescentar uma saída de erro a um componente, você deve fornecer o código que lida com as condições de erro ou truncamento específicas do componente e redireciona as linhas de erro ou truncamento para a saída de erro.</span><span class="sxs-lookup"><span data-stu-id="aba46-135">After adding an error output to a component, you must provide code that handles the error or truncation conditions specific to the component and redirects the error or truncation rows to the error output.</span></span> <span data-ttu-id="aba46-136">Você pode fazer isso de dois modos, dependendo se a saída de erro é síncrona ou assíncrona.</span><span class="sxs-lookup"><span data-stu-id="aba46-136">You can do this in two ways, depending on whether the error output is synchronous or asynchronous.</span></span>  
  
### <a name="redirecting-a-row-with-synchronous-outputs"></a><span data-ttu-id="aba46-137">Redirecionando uma linha com saídas síncronas</span><span class="sxs-lookup"><span data-stu-id="aba46-137">Redirecting a Row with Synchronous Outputs</span></span>  
 <span data-ttu-id="aba46-138">São enviadas linhas a saídas síncronas chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> da classe <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="aba46-138">Rows are sent to synchronous outputs by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> class.</span></span> <span data-ttu-id="aba46-139">A chamada do método inclui como parâmetros a ID da saída de erro, o código de erro definido pelo componente e o índice da coluna que o componente não conseguiu processar.</span><span class="sxs-lookup"><span data-stu-id="aba46-139">The method call includes as parameters the ID of the error output, the component-defined error code, and the index of the column that the component was unable to process.</span></span>  
  
 <span data-ttu-id="aba46-140">O exemplo de código seguinte demonstra como direcionar uma linha em um buffer para uma saída de erro síncrona que usa o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="aba46-140">The following code example demonstrates how to direct a row in a buffer to a synchronous error output using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput(int inputID, PipelineBuffer buffer)  
{  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
  
        // This code sample assumes the component has two outputs, one the default,  
        // the other the error output. If the errorOutputIndex returned from GetErrorOutputInfo  
        // is 0, then the default output is the second output in the collection.  
        int defaultOutputID = -1;  
        int errorOutputID = -1;  
        int errorOutputIndex = -1;  
  
        GetErrorOutputInfo(ref errorOutputID,ref errorOutputIndex);  
  
        if (errorOutputIndex == 0)  
            defaultOutputID = ComponentMetaData.OutputCollection[1].ID;  
        else  
            defaultOutputID = ComponentMetaData.OutputCollection[0].ID;  
  
        while (buffer.NextRow())  
        {  
            try  
            {  
                // TODO: Implement code to process the columns in the buffer row.  
  
                // Ideally, your code should detect potential exceptions before they occur, rather  
                // than having a generic try/catch block such as this.   
                // However, because the error or truncation implementation is specific to each component,  
                // this sample focuses on actually directing the row, and not a single error or truncation.  
  
                // Unless an exception occurs, direct the row to the default   
                buffer.DirectRow(defaultOutputID);  
            }  
            catch  
            {  
                // Yes, has the user specified to redirect the row?  
                if (input.ErrorRowDisposition == DTSRowDisposition.RD_RedirectRow)  
                {  
                    // Yes, direct the row to the error output.  
                    // TODO: Add code to include the errorColumnIndex.  
                    buffer.DirectErrorRow(errorOutputID, 0, errorColumnIndex);  
                }  
                else if (input.ErrorRowDisposition == DTSRowDisposition.RD_FailComponent || input.ErrorRowDisposition == DTSRowDisposition.RD_NotUsed)  
                {  
                    // No, the user specified to fail the component, or the error row disposition was not set.  
                    throw new Exception("An error occurred, and the DTSRowDisposition is either not set, or is set to fail component.");  
                }  
                else  
                {  
                    // No, the user specified to ignore the failure so   
                    // direct the row to the default output.  
                    buffer.DirectRow(defaultOutputID);  
                }  
  
            }  
        }  
}  
```  
  
```vb  
Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
   Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)   
  
   ' This code sample assumes the component has two outputs, one the default,  
   ' the other the error output. If the errorOutputIndex returned from GetErrorOutputInfo  
   ' is 0, then the default output is the second output in the collection.  
   Dim defaultOutputID As Integer = -1   
   Dim errorOutputID As Integer = -1   
   Dim errorOutputIndex As Integer = -1   
  
   GetErrorOutputInfo(errorOutputID, errorOutputIndex)   
  
   If errorOutputIndex = 0 Then   
     defaultOutputID = ComponentMetaData.OutputCollection(1).ID   
   Else   
     defaultOutputID = ComponentMetaData.OutputCollection(0).ID   
   End If   
  
   While buffer.NextRow   
     Try   
       ' TODO: Implement code to process the columns in the buffer row.  
  
       ' Ideally, your code should detect potential exceptions before they occur, rather  
       ' than having a generic try/catch block such as this.   
       ' However, because the error or truncation implementation is specific to each component,  
       ' this sample focuses on actually directing the row, and not a single error or truncation.  
  
       ' Unless an exception occurs, direct the row to the default   
       buffer.DirectRow(defaultOutputID)   
     Catch   
       ' Yes, has the user specified to redirect the row?  
       If input.ErrorRowDisposition = DTSRowDisposition.RD_RedirectRow Then   
         ' Yes, direct the row to the error output.  
         ' TODO: Add code to include the errorColumnIndex.  
         buffer.DirectErrorRow(errorOutputID, 0, errorColumnIndex)   
       Else   
         If input.ErrorRowDisposition = DTSRowDisposition.RD_FailComponent OrElse input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed Then   
           ' No, the user specified to fail the component, or the error row disposition was not set.  
           Throw New Exception("An error occurred, and the DTSRowDisposition is either not set, or is set to fail component.")   
         Else   
           ' No, the user specified to ignore the failure so   
           ' direct the row to the default output.  
           buffer.DirectRow(defaultOutputID)   
         End If   
       End If   
     End Try   
   End While   
End Sub  
```  
  
### <a name="redirecting-a-row-with-asynchronous-outputs"></a><span data-ttu-id="aba46-141">Redirecionando uma linha com saídas assíncronas</span><span class="sxs-lookup"><span data-stu-id="aba46-141">Redirecting a Row with Asynchronous Outputs</span></span>  
 <span data-ttu-id="aba46-142">Em vez de direcionar linhas para uma saída, como é feito com saídas de erro síncronas, os componentes com saídas assíncronas enviam uma linha para uma saída de erro acrescentando explicitamente uma linha à saída <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="aba46-142">Instead of directing rows to an output, as is done with synchronous error outputs, components with asynchronous outputs send a row to an error output by explicitly adding a row to the output <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span></span> <span data-ttu-id="aba46-143">Implementar um componente que usa saídas de erro assíncronas requer a adição de colunas à saída de erro, que são fornecidas a componentes downstream, e armazenando em cache o buffer de saída para a saída de erro que é fornecida ao componente durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="aba46-143">Implementing a component that uses asynchronous error outputs requires adding columns to the error output that are provided to downstream components, and caching the output buffer for the error output that is provided to the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="aba46-144">Os detalhes de implementação de um componente com saídas assíncronas são abordados em detalhes no tópico [Desenvolver um componente de transformação personalizado com saídas assíncronas](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="aba46-144">The details of implementing a component with asynchronous outputs are covered in detail in the topic [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span> <span data-ttu-id="aba46-145">Se as colunas não forem adicionadas explicitamente à saída de erro, a linha do buffer que é acrescentada ao buffer de saída conterá somente as duas colunas de erro.</span><span class="sxs-lookup"><span data-stu-id="aba46-145">If columns are not explicitly added to the error output, the buffer row that is added to the output buffer contains only the two error columns.</span></span>  
  
 <span data-ttu-id="aba46-146">Para enviar uma linha a uma saída de erro assíncrona, você deve acrescentar uma linha ao buffer de saída de erro.</span><span class="sxs-lookup"><span data-stu-id="aba46-146">To send a row to an asynchronous error output, you must add a row to the error output buffer.</span></span> <span data-ttu-id="aba46-147">Às vezes, uma linha já pode ter sido acrescentada ao buffer de saída de não erro e você deve remover essa linha usando o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RemoveRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="aba46-147">Sometimes, a row may have already been added to the non-error output buffer and you must remove this row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RemoveRow%2A> method.</span></span> <span data-ttu-id="aba46-148">Em seguida, você define os valores das colunas do buffer de saída e, finalmente, chama o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> para fornecer o código de erro específico do componente e o valor da coluna de erro.</span><span class="sxs-lookup"><span data-stu-id="aba46-148">Next you set the output buffer columns values, and finally, you call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method to provide the component-specific error code and the error column value.</span></span>  
  
 <span data-ttu-id="aba46-149">O exemplo seguinte demonstra como usar uma saída de erro para um componente com saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="aba46-149">The following example demonstrates how to use an error output for a component with asynchronous outputs.</span></span> <span data-ttu-id="aba46-150">Quando o erro simulado ocorre, o componente adiciona uma linha ao buffer da saída de erro, copia os valores que foram adicionados anteriormente ao buffer da saída de não erro para o buffer da saída de erro, remove a linha que foi adicionada ao buffer da saída de não erro e, finalmente, define o código de erro e os valores da coluna de erro chamando o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A>.</span><span class="sxs-lookup"><span data-stu-id="aba46-150">When the simulated error occurs, the component adds a row to the error output buffer, copies the values that were previously added to the non-error output buffer to the error output buffer, removes the row that was added to the non-error output buffer, and, finally, sets the error code and error column values by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method.</span></span>  
  
```csharp  
int []columnIndex;  
int errorOutputID = -1;  
int errorOutputIndex = -1;  
  
public override void PreExecute()  
{  
    IDTSOutput100 defaultOutput = null;  
  
    this.GetErrorOutputInfo(ref errorOutputID, ref errorOutputIndex);  
    foreach (IDTSOutput100 output in ComponentMetaData.OutputCollection)  
    {  
        if (output.ID != errorOutputID)  
            defaultOutput = output;  
    }  
  
    columnIndex = new int[defaultOutput.OutputColumnCollection.Count];  
  
    for(int col =0 ; col < defaultOutput.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 column = defaultOutput.OutputColumnCollection[col];  
        columnIndex[col] = BufferManager.FindColumnByLineageID(defaultOutput.Buffer, column.LineageID);  
    }  
}  
  
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        if (outputIDs[x] == errorOutputID)  
            this.errorBuffer = buffers[x];  
        else  
            this.defaultBuffer = buffers[x];  
    }  
  
    int rows = 100;  
  
    Random random = new Random(System.DateTime.Now.Millisecond);  
  
    for (int row = 0; row < rows; row++)  
    {  
        try  
        {  
            defaultBuffer.AddRow();  
  
            for (int x = 0; x < columnIndex.Length; x++)  
                defaultBuffer[columnIndex[x]] = random.Next();  
  
            // Simulate an error.  
            if ((row % 2) == 0)  
                throw new Exception("A simulated error.");  
        }  
        catch  
        {  
            // Add a row to the error buffer.  
            errorBuffer.AddRow();  
  
            // Get the values from the default buffer  
            // and copy them to the error buffer.  
            for (int x = 0; x < columnIndex.Length; x++)  
                errorBuffer[columnIndex[x]] = defaultBuffer[columnIndex[x]];  
  
            // Set the error information.  
            errorBuffer.SetErrorInfo(errorOutputID, 1, 0);  
  
            // Remove the row that was added to the default buffer.  
            defaultBuffer.RemoveRow();  
        }  
    }  
  
    if (defaultBuffer != null)  
        defaultBuffer.SetEndOfRowset();  
  
    if (errorBuffer != null)  
        errorBuffer.SetEndOfRowset();  
}  
```  
  
```vb  
Private columnIndex As Integer()   
Private errorOutputID As Integer = -1   
Private errorOutputIndex As Integer = -1   
  
Public  Overrides Sub PreExecute()   
 Dim defaultOutput As IDTSOutput100 = Nothing   
 Me.GetErrorOutputInfo(errorOutputID, errorOutputIndex)   
 For Each output As IDTSOutput100 In ComponentMetaData.OutputCollection   
   If Not (output.ID = errorOutputID) Then   
     defaultOutput = output   
   End If   
 Next   
 columnIndex = New Integer(defaultOutput.OutputColumnCollection.Count) {}   
 Dim col As Integer = 0   
 While col < defaultOutput.OutputColumnCollection.Count   
   Dim column As IDTSOutputColumn100 = defaultOutput.OutputColumnCollection(col)   
   columnIndex(col) = BufferManager.FindColumnByLineageID(defaultOutput.Buffer, column.LineageID)   
   System.Math.Min(System.Threading.Interlocked.Increment(col),col-1)   
 End While   
End Sub   
  
Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())   
 Dim x As Integer = 0   
 While x < outputs   
   If outputIDs(x) = errorOutputID Then   
     Me.errorBuffer = buffers(x)   
   Else   
     Me.defaultBuffer = buffers(x)   
   End If   
   System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
 End While   
 Dim rows As Integer = 100   
 Dim random As Random = New Random(System.DateTime.Now.Millisecond)   
 Dim row As Integer = 0   
 While row < rows   
   Try   
     defaultBuffer.AddRow   
     Dim x As Integer = 0   
     While x < columnIndex.Length   
       defaultBuffer(columnIndex(x)) = random.Next   
       System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
     End While   
     ' Simulate an error.  
     If (row Mod 2) = 0 Then   
       Throw New Exception("A simulated error.")   
     End If   
   Catch   
     ' Add a row to the error buffer.  
     errorBuffer.AddRow   
     ' Get the values from the default buffer  
     ' and copy them to the error buffer.  
     Dim x As Integer = 0   
     While x < columnIndex.Length   
       errorBuffer(columnIndex(x)) = defaultBuffer(columnIndex(x))   
       System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
     End While   
     ' Set the error information.  
     errorBuffer.SetErrorInfo(errorOutputID, 1, 0)   
     ' Remove the row that was added to the default buffer.  
     defaultBuffer.RemoveRow   
   End Try   
   System.Math.Min(System.Threading.Interlocked.Increment(row),row-1)   
 End While   
 If Not (defaultBuffer Is Nothing) Then   
   defaultBuffer.SetEndOfRowset   
 End If   
 If Not (errorBuffer Is Nothing) Then   
   errorBuffer.SetEndOfRowset   
 End If   
End Sub  
```  
  
<span data-ttu-id="aba46-151">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="aba46-151">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="aba46-152">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="aba46-152">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="aba46-153">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="aba46-153">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="aba46-154">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="aba46-154">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba46-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aba46-155">See Also</span></span>  
 <span data-ttu-id="aba46-156">[Tratamento de erro em dados](../../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="aba46-156">[Error Handling in Data](../../data-flow/error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="aba46-157">Usar saídas de erro</span><span class="sxs-lookup"><span data-stu-id="aba46-157">Using Error Outputs</span></span>](using-error-outputs-in-a-data-flow-component.md)  
  
  
