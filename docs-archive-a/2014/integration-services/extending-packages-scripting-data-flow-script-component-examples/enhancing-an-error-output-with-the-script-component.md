---
title: Aprimorando uma saída de erro com o componente Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], components
- Script component [Integration Services], examples
- error outputs [Integration Services], enhancing
- Script component [Integration Services], transformation components
ms.assetid: f7c02709-f1fa-4ebd-b255-dc8b81feeaa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 18637aa1e147ce989645ae859681929f4d0c438a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583172"
---
# <a name="enhancing-an-error-output-with-the-script-component"></a><span data-ttu-id="08260-102">Aprimorando uma saída de erro com o componente Script</span><span class="sxs-lookup"><span data-stu-id="08260-102">Enhancing an Error Output with the Script Component</span></span>
  <span data-ttu-id="08260-103">Por padrão, as duas colunas extras em uma saída de erro do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], ErrorCode e ErrorColumn, contêm apenas códigos numéricos que representam um número de erro e a ID da coluna na qual o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="08260-103">By default, the two extra columns in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error output, ErrorCode and ErrorColumn, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="08260-104">Esses valores numéricos podem ter uso limitado sem a descrição de erro correspondente.</span><span class="sxs-lookup"><span data-stu-id="08260-104">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="08260-105">Este tópico descreve como acrescentar uma coluna de descrição de erro a dados de saída de erro existentes no fluxo de dados usando o componente Script.</span><span class="sxs-lookup"><span data-stu-id="08260-105">This topic describes how to add an error description column to existing error output data in the data flow by using the Script component.</span></span> <span data-ttu-id="08260-106">O exemplo adiciona a descrição de erro que corresponde a um código de erro específico e predefinido do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], usando o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> da interface do <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponível através da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> do componente Script.</span><span class="sxs-lookup"><span data-stu-id="08260-106">The example adds the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the Script component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08260-107">Se desejar criar um componente que possa ser reutilizado mais facilmente em várias tarefas de fluxo de dados e em vários pacotes, procure utilizar o código deste exemplo de componente Script como o ponto inicial de um componente de fluxo de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="08260-107">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="08260-108">Para obter mais informações, consulte [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="08260-108">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08260-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="08260-109">Example</span></span>  
 <span data-ttu-id="08260-110">O exemplo demonstrado aqui usa um componente Script configurado como uma transformação para acrescentar uma coluna de descrição de erro a dados de saída de erro existentes no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="08260-110">The example shown here uses a Script component configured as a transformation to add an error description column to existing error output data in the data flow.</span></span>  
  
 <span data-ttu-id="08260-111">Para obter mais informações sobre como configurar o componente Script para uso como uma transformação no fluxo de dados, consulte [criando uma transformação síncrona com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)e [criando uma transformação assíncrona com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="08260-111">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="08260-112">Para configurar esse exemplo de componente Script</span><span class="sxs-lookup"><span data-stu-id="08260-112">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="08260-113">Antes de criar o novo componente Script, configure um componente upstream no fluxo de dados para redirecionar linhas para sua saída de erro quando um erro ou truncamento ocorrer.</span><span class="sxs-lookup"><span data-stu-id="08260-113">Before creating the new Script component, configure an upstream component in the data flow to redirect rows to its error output when an error or truncation occurs.</span></span> <span data-ttu-id="08260-114">Por motivo de teste, você pode configurar um componente de forma a assegurar que os erros ocorram – por exemplo, configurando uma transformação Pesquisa entre duas tabelas em que a pesquisa vai falhar.</span><span class="sxs-lookup"><span data-stu-id="08260-114">For testing purposes, you may want to configure a component in a manner that ensures that errors will occur-for example, by configuring a Lookup transformation between two tables where the lookup will fail.</span></span>  
  
2.  <span data-ttu-id="08260-115">Adicione um novo componente Script à superfície de designer Fluxo de Dados e configure-o como uma transformação.</span><span class="sxs-lookup"><span data-stu-id="08260-115">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span>  
  
3.  <span data-ttu-id="08260-116">Conecte a saída de erro do componente upstream ao novo componente Script.</span><span class="sxs-lookup"><span data-stu-id="08260-116">Connect the error output from the upstream component to the new Script component.</span></span>  
  
4.  <span data-ttu-id="08260-117">Abra o **Editor de Transformação Scripts** e, na página **Script**, para a propriedade **ScriptLanguage**, selecione a linguagem de script.</span><span class="sxs-lookup"><span data-stu-id="08260-117">Open the **Script Transformation Editor**, and on the **Script** page, for the **ScriptLanguage** property, select the script language.</span></span>  
  
5.  <span data-ttu-id="08260-118">Clique em **Editar Script** para abrir o IDE do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSTA (Tools for Applications) e adicionar o código de exemplo mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="08260-118">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE and add the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="08260-119">Feche o VSTA.</span><span class="sxs-lookup"><span data-stu-id="08260-119">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="08260-120">No editor de transformação scripts, na página **colunas de entrada** , selecione a coluna ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="08260-120">In the Script Transformation Editor, on the **Input Columns** page, select the ErrorCode column.</span></span>  
  
8.  <span data-ttu-id="08260-121">Na página **entradas e saídas** , adicione uma nova coluna de saída do tipo `String` chamado **ErrorDescription**.</span><span class="sxs-lookup"><span data-stu-id="08260-121">On the **Inputs and Outputs** page, add a new output column of type `String` named **ErrorDescription**.</span></span> <span data-ttu-id="08260-122">Aumente o comprimento padrão da coluna nova para 255 para suportar mensagens longas.</span><span class="sxs-lookup"><span data-stu-id="08260-122">Increase the default length of the new column to 255 to support long messages.</span></span>  
  
9. <span data-ttu-id="08260-123">Feche o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="08260-123">Close the **Script Transformation Editor.**</span></span>  
  
10. <span data-ttu-id="08260-124">Anexe a saída do componente Script a um destino satisfatório.</span><span class="sxs-lookup"><span data-stu-id="08260-124">Attach the output of the Script component to a suitable destination.</span></span> <span data-ttu-id="08260-125">Um destino de arquivo simples é o mais fácil de configurar para testar ad hoc.</span><span class="sxs-lookup"><span data-stu-id="08260-125">A Flat File destination is the easiest to configure for ad hoc testing.</span></span>  
  
11. <span data-ttu-id="08260-126">Execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="08260-126">Run the package.</span></span>  
  
```vb  
Public Class ScriptMain  
    Inherits UserComponent  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  Row.ErrorDescription = _  
    Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain:  
    UserComponent  
{  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
  Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
    }  
}  
  
```  
  
<span data-ttu-id="08260-127">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="08260-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="08260-128">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="08260-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="08260-129">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="08260-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="08260-130">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="08260-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08260-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08260-131">See Also</span></span>  
 <span data-ttu-id="08260-132">[Tratamento de erro em dados](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="08260-132">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="08260-133">[Usando saídas de erro em um componente de fluxo de dados](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="08260-133">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="08260-134">Criar uma transformação síncrona com o componente de Script</span><span class="sxs-lookup"><span data-stu-id="08260-134">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
